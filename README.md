[![Build Status](https://secure.travis-ci.org/Laiff/react-lensed-state.svg?branch=master)](https://travis-ci.org/Laiff/react-lensed-state)
[![NPM version](https://badge.fury.io/js/react-lensed-state.svg)](http://badge.fury.io/js/react-lensed-state)
[![Dependencies Status](https://david-dm.org/Laiff/react-lensed-state.svg?style=flat-square)](https://david-dm.org/Laiff/react-lensed-state)
[![experimental](http://hughsk.github.io/stability-badges/dist/experimental.svg)](http://github.com/hughsk/stability-badges)

react-lensed-state
==================

Adds react opportunity to work with the state in a hierarchical notation, for example this.linkState ('model.user.name') will point to the part of the object state. Work of lens are immutable, that is, after changing the value will create a new state object.

## Example

``` js
var LensedExample = React.createClass({
  
      mixins : [LensedStateMixin],
 
      getInitialState : {
          model : {
              user : {
                  name: "John",
                  email: "john@example.com"
              },
              notify : {
                  email : true,
                  fb: false
              }
          }
      },
 
      render: function() {
          return (
              <form>
                  <input valueLink={this.linkState('model.user.name')} type="text" name="user-name" />
                  <input valueLink={this.linkState('model.user.email')} type="text" name="user-email" />
                  <input valueLink={this.linkState('model.notify.email')} type="checkbox" name="notify-email" />
                  <input valueLink={this.linkState('model.notify.fb')} type="checkbox" name="notify-fb" />
             </form>
          );
      }
  });
```
## Installing

The easiest way is to grab it from NPM. If you're running in a Browser
environment, you can use [Browserify][]

    $ npm install react-lensed-state

[![NPM](https://nodei.co/npm/react-lensed-state.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/react-lensed-state/)
