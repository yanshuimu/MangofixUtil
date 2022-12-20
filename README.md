# MangoFixUtil

对[MangoFix](https://github.com/YPLiang19/Mango)做了简单的封装，该库在OC项目中实战已经近2年多，经过多次迭代，比较成熟。

另有自己维护的[补丁管理后台](http://patchhub.top/mangofix/login)，目前已经有40+个已上架AppStore的应用在使用，且有日活1w+的应用，欢迎小伙伴们使用。

## Example

```objc
@implementation AppDelegate

- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    
    [self setupMangoFixUtil];
    
    self.window = [[UIWindow alloc] initWithFrame:[UIScreen mainScreen].bounds];
    self.window.backgroundColor = [UIColor whiteColor];
    self.window.rootViewController = [[ViewController alloc] init];
    [self.window makeKeyAndVisible];
            
    return YES;
}

- (void)setupMangoFixUtil {
    
    [[MangoFixUtil startWithAppId:APPID aesKey:AES128KEY] evalRemoteMangoScript];
}

@end
```
## Installation

### CocoaPods

```ruby
# Your Podfile
pod 'MangoFixUtil'
```

## Usage

### Objective-C
1. `#import <MangoFixUtil/MangoFixUtil.h>`

```objc
MangoFixUtil *mangoFixUtil = [MangoFixUtil sharedUtil];
[mangoFixUtil startWithAppId:APPID aesKey:AES128KEY];

// exec mangofix file from network
[mangoFixUtil evalRemoteMangoScript];

// exec local mangofix file
[mangoFixUtil evalLocalEncryptedMangoScript];

// exec local unEncrypted mangofix file
[mangoFixUtil evalLocalUnEncryptedMangoScript];

// encrypt plain mangofix file to documentDirectory
[mangoFixUtil encryptPlainScriptToDocument];

```
## Update

#### V2.1.2
1. 使用MangoFix.framework（版本：1.5.2）替换CocoaPods依赖以支持Swift项目使用。
2. 简化代码，优化流程。

#### V2.1.1
1. 支持通过UserId、BundleId识别唯一App。

#### V2.1.0
1. 支持AES加密方式，适配MangoFix 1.5.0以上版本。

#### V2.0.4
1. 支持日活量统计。

#### V2.0.3
1. 优化流程。

#### V2.0.2
1. 支持线上加密补丁。

#### V2.0.1
1. 优化。

#### V2.0.0
1. 支持设备数、激活数统计。

#### V1.0.6
1. 发布支持开发设备、全量设备。

## Thanks for
[Mango](https://github.com/YPLiang19/Mango)
