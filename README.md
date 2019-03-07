# amazon-fling
Amazon Fling

Easily integrate the *Amazon Fling SDK* to discover and control your FireTV in your app

[![Platform](https://img.shields.io/badge/platform-iOS-lightgrey.svg?longCache=true&style=flat-square)](https://www.apple.com/de/ios)
[![License](https://img.shields.io/badge/license-MIT-lightgrey.svg?longCache=true&style=flat-square)](https://en.wikipedia.org/wiki/MIT_License)

## Example

Import *AmazonFling* and start using the SDK:

```objective-c
#import <AmazonFling/DiscoveryController.h>
#import <AmazonFling/RemoteMediaPlayer.h>
#import <AmazonFling/MediaPlayerStatus.h>

@implementation AppDelegate
...
- (void)applicationDidBecomeActive:(UIApplication *)application {
    id myViewController = [self findViewController];
    [myViewController resume];
}
...
@implementation ViewController
...
- (void)viewDidLoad {
...
    mController = [[DiscoveryController alloc] init];
    [mController searchPlayerWithId : @"amzn.thin.pl" andListener : self];
}

- (void)resume {
    [mController resume];
}

- (void)deviceDiscovered:(id<RemoteMediaPlayer>)device {
    [mDevices addObject:device];
    // Update UI
}

- (void)deviceLost:(id<RemoteMediaPlayer>)device {
    [mDevices removeObject:device];
    // Update UI
}

- (void)discoveryFailure {
}
```

## Requirements

You need to install `git lfs` because the Amazon Fling binary is too large for a normal git repository. You can do this via [Homebrew](https://brew.sh) using `brew install git-lfs`. For more information visit [Git LFS](https://git-lfs.github.com/).

## Changelog

[Amazon Fling SDK Release Notes](https://developer.amazon.com/docs/fling/release-notes.html)

## License

*AmazonFling* is available under the MIT license. See the LICENSE file for more info.
