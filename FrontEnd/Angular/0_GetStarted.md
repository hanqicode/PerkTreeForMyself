# Get Started

[Angular Document](https://angular.io/docs)

## Components
A component consists of three things:
- A component class that handles data and functionality.
- An HTML template that determines the UI.
- Component-specific styles that define the look and feel.

```javascript
import { Component } from '@angular/core';

@Component({
  selector: 'hello-world',
  template: `
    <h2>Hello World</h2>
    <p>This is my first component!</p>
    `,
})
export class HelloWorldComponent {
  // The code in this class drives the component's behavior.
}
```
To use this component, you write the following in a template:
```javascript
<hello-world></hello-world>
```
When Angular renders this component, the resulting DOM looks like this:
```javascript
<hello-world>
    <h2>Hello World</h2>
    <p>This is my first component!</p>
</hello-world>
```

## Templates
Angular extends HTML with additional syntax that lets you insert **dynamic** values from your component.

```javascript
<p>{{ message }}</p>
```

The value for message comes from the component class:
```javascript
import { Component } from '@angular/core';

@Component ({
  selector: 'hello-world-interpolation',
  templateUrl: './hello-world-interpolation.component.html'
})
export class HelloWorldInterpolationComponent {
    message = 'Hello, World!';
}
```

## Getting started with Angular
