# Firework iOS Specs

The CocoaPods specs repository for the Firework iOS SDKs.

CocoaPods trunk became read-only on December 2, 2026, so new versions of the Firework pods are published here instead of to trunk. Versions released before that date stay available from the CocoaPods CDN.

## Pods

| Pod | Source repository |
| --- | --- |
| `FireworkVideo` | [firework_ios_sdk](https://github.com/loopsocial/firework_ios_sdk) |
| `FireworkVideo-Static` | [firework_ios_sdk](https://github.com/loopsocial/firework_ios_sdk) |
| `FireworkVideoUI` | [firework_ios_sdk_ui_extensions](https://github.com/loopsocial/firework_ios_sdk_ui_extensions) |
| `FireworkVideoIVSSupport` | [firework_ios_sdk_ivs_support](https://github.com/loopsocial/firework_ios_sdk_ivs_support) |
| `FireworkVideoAgoraSupport` | [firework_ios_sdk_agora_support](https://github.com/loopsocial/firework_ios_sdk_agora_support) |

## Usage

Add both sources to the top of your `Podfile`:

```ruby
source 'https://github.com/loopsocial/firework_ios_specs.git'
source 'https://cdn.cocoapods.org/'

target 'YourApp' do
  pod 'FireworkVideo'
end
```

Keep the `cdn.cocoapods.org` line. Once a `Podfile` declares any `source`, CocoaPods no longer adds the CDN by default, and pods such as `AmazonIVSPlayer` and `AgoraRtcEngine_iOS`, as well as Firework versions released before December 2, 2026, are only available there.

Then run:

```bash
pod install --repo-update
```

## Publishing

Specs are pushed by the release workflows of the source repositories. Do not edit this repository by hand.

To publish manually:

```bash
pod repo add firework_ios_specs git@github.com:loopsocial/firework_ios_specs.git
pod repo push firework_ios_specs FireworkVideo.podspec \
  --sources=firework_ios_specs,https://cdn.cocoapods.org/
```
