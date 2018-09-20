# BufferRendering
Renders animated graphics in a memory buffer and displays it on the screen using standard Apple's Technologies.

# Overview

Proof of concept of how to use Apple's Standard Technologies to create a simple VJing rendering mechanism that:

- renders the content in memory in real time
- allows for several layers
- is flicker free
- allows effects
- uses standard frameworks/libraries

# Investigation

## Points of investigation to find solutions for

- how to have an in-memory layer stack to use for drawing-rendering

## Already tried

### Using an NSViews

This looked like the first place to try. Having an in-memory (not displayed) `NSView` and use it's layer property to draw into.

####  Problems found

##### How to draw this view in the output view. 

Maybe make it a subview of a view or create an image out of this view and draw it on the displaying views. 
It looks like it's overkill, too intensive and complex. overall a really bad idea

## Needs trying

### Using an `NSImage`

#### Links

- https://developer.apple.com/documentation/appkit/nsimage?language=objc


### Direclty using an `CALayer`

Subclass a `CALayer` and use it to draw the content. Check if a delegate object is needed or is a good approach.

use ` drawInContext` to draw in a view context. Maybe the delegate does this?!


```
- (void)drawInContext:(CGContextRef)ctx;
```

#### Links

- https://developer.apple.com/documentation/quartzcore/calayer?language=objc



# Credits

2018 Daniel Almeida (danielf.almeida -at- gmail.com) 
