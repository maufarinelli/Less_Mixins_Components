LESS mixin's components
======================

What I mean about LESS components? I mean some reusable component you created, following the [SMACSS](https://smacss.com/) concept 

*.component* and its specific styles as *.component--types* (in the same level)
* *.component-child~~* and its specific styles as *.component-child--types* (in the same level)

Using the following syntax:
* simple class for a **component**
* a class including the **component class**, **--** and a **type name** to define a component type
* a class including the **component class**, **-** and a **child name** to define a component child
* a class including the **component class child**, **--** and a **type name** to define a component child type

For example:
~~<button class="button button--delete">Delete<i class="button-icon button-icon--delete"></i></button>~~

For that we have 4 simple mixins to do this job

```
.component(@name, @rules) {
    .@{name} {
        @rules();
    }
}

.child(@parent, @name, @rules) {
    .@{parent}-@{name} {
        @rules();
    }
}

.type(@component, @name, @rules) {
    &.@{component}--@{name} {
        @rules();
    }
}

.state(@state, @rules) {
    &.is-@{state} {
        @rules();
    }
}
```

Enjoy it!
