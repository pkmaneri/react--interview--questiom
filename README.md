# react--interview--questiom
how virtual dom works? 
there are three simple steps 
A-whenever any underlying data changes,the entire ui is re-rendered in virtual dom representation.
B-then the difference between the previous dom representaion and the new one is calculate.
C-once the calculations is done, the real dom will be updated with only things that have actually change.

what is the difference between shadow dom and virtual dom?
-the shadow dom is a browser technology designed primarily for scoping variable and css in web components. the virtual dom is a concept implimented by libaries in javascripton top of browser APIs.

what is react fiber?
-  fiber is  the reconciliation engine. the goal of react fiber is  to increase its suitability for areas like animation, layout, and gestures. Its headline feature is incremental rendering: the ability to split rendering work into chunks and spread it out over multiple frames.
what are controlled component?
-a component that control that input elements within the froms on subsequent user input is called controlled component.ie,
that is every state mutation will have an associated handler function.
