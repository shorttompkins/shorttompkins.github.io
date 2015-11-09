layout: true

.twitter-handle[<i style="color: #55ACEE;" class="fa fa-twitter"></i> <i class="fa fa-github"></i> ShortTompkins]

---

class: center, middle

# Intro to React.js

<img src="img/react-logo.png" class="centered-image" style="width: 180px;"/>

### Bucks County JS .grey[|] 11/11/15

### Jason Krol

---

# About Me

.right-image[![alt text](img/jackburton.jpeg)]

## Jason Krol

<i style="color: #55ACEE;" class="fa fa-twitter"></i> <i class="fa fa-github"></i>  **ShortTompkins**<br/>
<i style="color: orange;" class="fa fa-rss"></i>  Kroltech.com
<br/>
<img src="img/dflogo.png" style="margin-bottom: 10px;"/>
<br/><br/>
Dad, Author, Gamer, Geek!

[shorttompkins.js.org/talks/bcjs_reactintro](http://shorttompkins.js.org/talks/bcjs_reactintro)
[**github.com/shorttompkins/bcjs_reactintro**](http://github.com/shorttompkins/bcjs_reactintro)

---

## What *is* React.js?

<img src="img/react-logo.png" style="width: 100px; margin-left: 100px;" /> <img src="img/facebook_2015_logo_detail.png" style="margin-left: 100px; width: 270px;" />

* Created by Facebook, Open Source
* Pure UI framework (i.e. the V in MV*)
* Virtual DOM
* Can render on the server (isomorphic)
* Everything is a component (modular)
* Currently version 0.14.2
* React-native

---

## React.js is *not*...

* fairly comparable to Angular, Ember, et al
* A full fledged framework
* A magic bullet

???
Some examples:

* super basic DOM manipulation (not preferred)
* no ajax tools!
* React can be used within Angular! (huh?!)

---

## What we'll talk about

* Some examples/demos
* JSX syntax
* Component lifecycle
* Component Props, State, and Events
* Intro to Flux

---

## A Super Basic Project

```javascript
// Gulpfile.js
gulp.task('transform', function () {
  browserify({
    entries: 'src/js/main.js',
    extensions: ['.js'],
    debug: true
  })
  .transform(babelify)
  .bundle()
  .pipe(source('app.js'))
  .pipe(gulp.dest('build'));
});
```

???

Explain babel, browserify, jsx transformation, etc.

---

## Simple Demo

```javascript
var App = React.createClass({
  render: function() {
    return (
      <div>
        Hello world!
      </div>
    );
  }
});

ReactDOM.render(<App />,
  document.getElementById('app'));
```

.live-demo[<a href="http://127.0.0.1:8080/samples/helloworld.html" class="fa fa-rocket" target="\_blank"></a>]

---

## What the heck is JSX?!

```jsx
render: function() {
  var foo = 'bar';
  return (
    <h1>Hello {foo}</h1>
  );
}
```

???

JavaScript syntax extension

---

## A components lifecycle

* `componentWillMount`
* `render`
* `componentDidMount`


* `componentWillUpdate`
* `shouldComponentUpdate`
* `componentWillReceiveProps`
* `shouldComponentUpdate`
* `componentDidUpdate`
* `componentWillUnmount` - Cleanup

---

## `this.props`

```javascript
render: function() {
  return (
    <div>
      <h1>{this.props.name}</h1>
      <span>{this.props.twitter}</span>
    </div>
  );
}
```

```html
<Person name='Jason' twitter='blah' />
```

.live-demo[<a href="http://127.0.0.1:8080/samples/person.html" class="fa fa-rocket" target="\_blank"></a>]

---

## `this.state`

```javascript
increaseCounter: function() {
* this.setState({
    counter: this.state.counter + 1
  });
},
render: function() {
  return (
    <h1 onClick={this.increaseCounter}>
      Counter: {this.state.counter}
    </h1>
  );
}
```

.live-demo[<a href="http://127.0.0.1:8080/samples/statecounter.html" class="fa fa-rocket" target="\_blank"></a>]

---

## Nesting Components

```javascript
render: function() {
  var people =
    myPeople.map(function(person){
      return (
*       <Person name={person.name} />
      );
  });
  return (
    <div>
      {people}
    </div>
  );
```

.live-demo[<a href="http://127.0.0.1:8080/samples/people.html" class="fa fa-rocket" target="\_blank"></a>]

---

## What is FLUX?

<img src="img/flux-diagram.png" style="width: 80%; margin-left: 10%;" />

* Unidirectional Data Flow
* Single source of truth (Store)
* Heavily Event driven (Actions)
* Unlike what you're used to! (!=MVC)

---

## Popular Flux Frameworks

* [Redux](http://redux.js.org/)
* [Alt](http://alt.js.org/)
* [Reflux](https://github.com/reflux/refluxjs)
* [Fluxxor](http://fluxxor.com/)

---

## Resources

* [egghead.io](http://egghead.io)
* [React docs](https://facebook.github.io/react/docs/getting-started.html)
* [React blog (important!)](https://facebook.github.io/react/blog/)
* [Flux Overview](https://facebook.github.io/flux/docs/overview.html)
* [React Discord community](http://join.reactiflux.com)
* [Slack PhillyDev](http://phillydev.org/) #philly-react channel
* [react-sandbox](https://github.com/shorttompkins/react_sandbox)
* [MRW.lol repo & articles](https://github.com/shorttompkins/mrw.lol)

---

class: center, middle

# Thanks!
