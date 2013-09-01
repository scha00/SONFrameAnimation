SONFrameAnimation
=================

`SONFrameAnimation` is an iOS class that supports to display still frames of desired position in your custom animation.  
It allows you to perform ‘animate as you pinch (or pan, scroll) effect’, and also can animate forward or backward from the specific position.  
`SONFrameAnimationGroup` is a group of `SONFrameAnimation`s. By using this class, you can create more complex custom animations by grouping several `SONFrameAnimation` objects.  
Features in `SONFrameAnimation` such as still frame, resume, and rewind animation can also be used with the group.  



Usage
----------------

Example:

    SONFrameAnimation *anim1 = [[SONFrameAnimation alloc] initWithKeyPath:@"transform.scale" fromValue:[NSNumber numberWithFloat:1.0] toValue:[NSNumber numberWithFloat:2.0]];
    anim1.duration = 1.0;
    
    SONFrameAnimationGroup *animGroup = [[SONFrameAnimationGroup alloc] initWithAnimations:[NSArray arrayWithObject:anim1]];
    animGroup.duration = 1.0;
    animGroup.rewindDuration = 0.3;
    
    // Still frame
    [animGroup stillFrameView:testView position:0.5];
    
    // Resume
    [animGroup resumeAnimationForView:testView fromPosition:0.5];
    
    // Rewind
    [animGroup rewindAnimationForView:testView fromPosition:0.5];

    
Setting
----------------

`timingFunction` is a property that will let you set CAMediaTimingFunction object for your animation.  
`initialValue` is a property that is needed to be set if `fromValue` property is not identical to the inital state of the view.  

`rewindDuration` is a `SONFrameAnimationGroup` property that decides the duration when rewinding the animation from any position. Setting the property to 0.0 will adjust its duration according to the animation duration and the position. Initial Value is 0.0.  


Etc
----------------

As this build is experimental, it may not always work as intended.  
For `SONFrameAnimationGroup` class, rewind animation will not exactly trace back your animation but will restore to the initial state.  

    
Links
----------------

- Website: [www.soncode.com](http://www.soncode.com)
- Blog: [tumblr.soncode.com](http://tumblr.soncode.com)
