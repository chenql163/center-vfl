# Centering a view in a super view with visual format language using Auto Layout in iOS

This is an example of centeing a label in its view using [Visual Format Language](http://developer.apple.com/library/mac/#documentation/UserExperience/Conceptual/AutolayoutPG/Articles/formatLanguage.html#//apple_ref/doc/uid/TP40010853-CH3-SW1).

Here is the code from [view controller](https://github.com/evgenyneu/center-vfl/blob/master/CenteringWithVFL/CenteringWithVFLViewController.m) that does the trick:

```ObjectiveC
UIView *superview = self.view;
NSDictionary *variables = NSDictionaryOfVariableBindings(label, superview);
NSArray *constraints =
[NSLayoutConstraint constraintsWithVisualFormat:@"V:[superview]-(<=1)-[label]"
                                        options: NSLayoutFormatAlignAllCenterX
                                        metrics:nil
                                          views:variables];
[self.view addConstraints:constraints];

constraints =
[NSLayoutConstraint constraintsWithVisualFormat:@"H:[superview]-(<=1)-[label]"
                                        options: NSLayoutFormatAlignAllCenterY
                                        metrics:nil
                                          views:variables];
[self.view addConstraints:constraints];
```
    

<img src='https://raw.github.com/evgenyneu/center-vfl/master/centering_with_vfl.png' width='568' alt='Centering in superview with VFL'>
