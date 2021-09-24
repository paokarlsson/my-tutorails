# Two ways to pass a function from a parent component to a child component



<strong>#angular #observerpattern #childtoparent #componentcommunication</strong>

## 1. Using the @Input() tag in the child component

Parent component
```js
import { Component } from '@angular/core';

@Component({
  selector: 'app-parent',
  template: `<app-child  [parentFunction]="parentFunction"></app-child>`
})
export class ParentComponent {

  parentFunction = (text:string):void => {
    console.log("This is parentFunction. Hello " + text + "!")
  }
}
```

Child component
```js
import { Component, Input } from '@angular/core';

@Component({
  selector: 'app-child',
  template: `<button (click)="executeParentFunction()">Click</button>`
})
export class ChildComponent {

  @Input() parentFunction!:(text:string)=> void;

  executeParentFunction() {
    this.parentFunction("Some text");
  }
}
```

## 2. Using Output() and EventEmitter in childcomponent

Parent component
```js
import { Component } from '@angular/core';

@Component({
  selector: 'app-parent',
  template: `<app-child  (parentFunction)="parentFunction($event)"></app-child>`
})
export class ParentComponent {

  parentFunction = (text: string): void => {
    console.log("This is parentFunction. Hello " + text + "!")
  }
}
```

Child component
```js
import { Component, EventEmitter, Output } from '@angular/core';

@Component({
  selector: 'app-child',
  template: `<button (click)="executeParentFunction()">Click</button>`
})
export class ChildComponent {

  @Output('parentFunction') parentFunction: EventEmitter<string> = new EventEmitter();

  executeParentFunction() {
    this.parentFunction.emit("Some text");
  }
}
```