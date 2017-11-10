Animation exercise remember-me
===================

This is an implementation of an animation exercise for a remember me dialog box. The original inspiration was taken from a [medium.com article](https://medium.com/bridge-collection/improve-the-payment-experience-with-animations-3d1b0a9b810e).

The orignal animation gif:
![Example image](https://raw.githubusercontent.com/lassehav/animation-remember-me/master/remember_me.gif)

The implementation:
![Implentation](https://raw.githubusercontent.com/lassehav/animation-remember-me/master/implementation.gif)


----------


Main points
-------------

Main points in the implementation are the following:

#### Perspective
The perspective CSS definition controls the 3D rendering needed for a flip effect. The value itself defines how many pixels a 3D element is placed from the view.

    perspective: 600px;

Important to notice is that the perspective CSS definition needs to be used by the parent of the actual element doing the flip effect.

#### Transform

The actual flip effect is achived by toggling the rotateX value of the transform property.
The transform-origin defines the 'hinge' eg. the origin point for the flip.

    .collapse
    {
	    ...
	    transform: rotateX(-90deg);
	    transform-origin: 0px 0px;
	}
	.collapse-visible
	{
		...
		transform: rotateX(0deg);
	}

#### Custom transition timing function
A custom transition timing function is used to achieve the followthrough / overshoot animation effect.

    transition-timing-function: cubic-bezier(0.730, 0.005, 0.265, 1.550);

