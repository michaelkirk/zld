benchmarks in the graph were done on a high-end mac desktop

high-end mac desktop numbers (ms):
signal: 390, 250
mozilla XUL: 5.2s, 2.20s
mozilla's storage.framework: 495, 340

there was also benchmarking done on a 2014 macbook pro, to give a sense of lower-end numbers. the % speedup was roughly the same across the 3 benchmarks

2014 macbook pro numbers (ms):
signal: 790, 540
mozilla XUL: 10.3s, 5.4s
mozilla's storage.framework: 940, 625



signal
the main app binary for Signal (https://github.com/signalapp/Signal-iOS)

ld -no_uuid -demangle -lto_library /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/lib/libLTO.dylib -dynamic -arch x86_64 -ios_simulator_version_min 10.0.0 -syslibroot /Applications/Xcode.app/Contents/Developer/Platforms/iPhoneSimulator.platform/Developer/SDKs/iPhoneSimulator13.2.sdk -ObjC -o /Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/Signal.app/Signal -L/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator -L/Users/michael/projects/Signal-iOS/Pods/../ThirdParty/WebRTC/Build/libringrtc -L/Users/michael/projects/Signal-iOS -L/Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/lib/swift/iphonesimulator -L/usr/lib/swift -rpath /usr/lib/swift -filelist /Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Intermediates.noindex/Signal.build/Debug-iphonesimulator/Signal.build/Objects-normal/x86_64/Signal.LinkFileList -rpath @executable_path/Frameworks -rpath @loader_path/Frameworks -rpath @executable_path/Frameworks -object_path_lto /Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Intermediates.noindex/Signal.build/Debug-iphonesimulator/Signal.build/Objects-normal/x86_64/Signal_lto.o -export_dynamic -no_deduplicate -objc_abi_version 2 -add_ast_path /Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Intermediates.noindex/Signal.build/Debug-iphonesimulator/Signal.build/Objects-normal/x86_64/Signal.swiftmodule -lc++ -lz -framework AFNetworking -framework AVFoundation -framework Accelerate -framework AssetsLibrary -framework AxolotlKit -framework CocoaLumberjack -framework CoreFoundation -framework CoreGraphics -framework CoreMedia -framework CoreTelephony -framework CoreVideo -framework Curve25519Kit -framework Foundation -framework GRDB -framework HKDFKit -framework ImageIO -framework Lottie -framework Mantle -framework MobileCoreServices -framework PromiseKit -framework PureLayout -framework QuartzCore -framework Reachability -framework SAMKeychain -framework SQLCipher -framework SSZipArchive -framework Security -framework SignalCoreKit -framework SignalMetadataKit -framework SignalRingRTC -framework SignalServiceKit -framework Starscream -framework SwiftProtobuf -framework SystemConfiguration -framework UIKit -framework WebRTC -framework YYImage -framework YapDatabase -framework ZXingObjC -framework blurhash -framework libPhoneNumber_iOS -framework libwebp -framework openssl -sectcreate __TEXT __entitlements /Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Intermediates.noindex/Signal.build/Debug-iphonesimulator/Signal.build/Signal.app-Simulated.xcent -weak_framework Metal -weak_framework MetalKit -weak_framework Intents -framework Photos -weak_framework ContactsUI -weak_framework Contacts -framework PushKit -framework Social -framework CoreMedia -framework MobileCoreServices -framework MessageUI -framework SignalMessaging -framework MediaPlayer -lz -framework QuartzCore -framework Security -framework AddressBook -framework AddressBookUI -framework CFNetwork -framework SystemConfiguration -framework CoreTelephony -framework UIKit -framework Foundation -framework AVFoundation -framework AudioToolbox -framework Pods_Signal -framework Foundation -lobjc -lSystem /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/lib/clang/11.0.0/lib/darwin/libclang_rt.ios.a -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator -F/Users/michael/projects/Signal-iOS/ThirdParty/WebRTC/Build -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/AFNetworking -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/AxolotlKit -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/CocoaLumberjack -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/Curve25519Kit -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/GRDB.swift -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/HKDFKit -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/Mantle -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/PromiseKit -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/PureLayout -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/Reachability -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/SAMKeychain -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/SQLCipher -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/SSZipArchive -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/SignalCoreKit -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/SignalMetadataKit -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/SignalRingRTC -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/SignalServiceKit -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/Starscream -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/SwiftProtobuf -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/YYImage -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/YapDatabase -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/blurhash -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/libPhoneNumber-iOS -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/libwebp -F/Users/michael/Library/Developer/Xcode/DerivedData/Signal-eaaymknzhulxsvdxstqxeyotiefd/Build/Products/Debug-iphonesimulator/lottie-ios -F/Users/michael/projects/Signal-iOS/Pods/../ThirdParty/WebRTC/Build -F/Users/michael/projects/Signal-iOS/Pods/GRKOpenSSLFramework/OpenSSL-iOS/bin -F/Users/michael/projects/Signal-iOS/Pods/YYImage/Vendor -F/Users/michael/projects/Signal-iOS/Pods/ZXingObjC -F/Users/michael/projects/Signal-iOS -print_statistics

XUL
XUL is a framework built as part of the OS X firefox app (https://developer.mozilla.org/en-US/docs/Mozilla/Developer_guide/Build_Instructions/Mac_OS_X_Prerequisites)

ld -no_uuid -dynamic -dylib -dylib_compatibility_version 1 -dylib_current_version 1 -arch x86_64 -dylib_install_name @executable_path/XUL -macosx_version_min 10.14.0 -single_module -syslibroot /Users/michael/projects/MacOSX-SDKs/MacOSX10.14.sdk -o XUL -L/opt/local/lib -filelist /Users/michael/projects/mozilla/mozilla-unified/obj-x86_64-apple-darwin18.5.0/toolkit/library/build/XUL.list -syslibroot /Users/michael/projects/MacOSX-SDKs/MacOSX10.14.sdk -framework Cocoa -lobjc -framework AudioToolbox -framework ExceptionHandling -U _OBJC_CLASS_$_NSTouchBar -U _OBJC_CLASS_$_NSSharingServicePickerTouchBarItem -U _OBJC_METACLASS_$_NSTouchBar -U _OBJC_CLASS_$_NSCustomTouchBarItem -U _OBJC_CLASS_$_NSPopoverTouchBarItem -lresolv -executable_path /Users/michael/projects/mozilla/mozilla-unified/obj-x86_64-apple-darwin18.5.0/dist/bin ../../../security/nss/lib/crmf/crmf_crmf/libcrmf.a ../../../js/src/build/libjs_static.a /Users/michael/projects/mozilla/mozilla-unified/obj-x86_64-apple-darwin18.5.0/x86_64-apple-darwin/release/libgkrust.a ../../../security/libnss3.dylib ../../../config/external/lgpllibs/liblgpllibs.dylib ../../../mozglue/build/libmozglue.dylib -framework IOSurface -framework IOKit -framework AudioToolbox -framework CoreMedia -framework VideoToolbox -framework Foundation -framework AVFoundation -framework CoreVideo -framework AppKit -framework OpenGL -framework LocalAuthentication -framework Security -lm -framework SystemConfiguration -framework CoreUI -framework CoreSymbolication -lcups -framework Foundation -framework CoreFoundation -framework CoreLocation -framework QuartzCore -framework Carbon -framework CoreAudio -framework CoreVideo -framework AudioToolbox -framework AudioUnit -framework AddressBook -framework OpenGL -framework Security -framework ServiceManagement -framework CoreServices -framework ApplicationServices -framework AppKit -weak_framework Metal -lc++ -lSystem /Users/michael/.mozbuild/clang/lib/clang/9.0.1/lib/darwin/libclang_rt.osx.a -F/System/Library/PrivateFrameworks

storage
Storage is a framework built as part of the iOS firefox app (https://github.com/mozilla-mobile/firefox-ios)

ld -demangle -application_extension -lto_library /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/lib/libLTO.dylib -dynamic -dylib -dylib_compatibility_version 1 -dylib_current_version 1 -arch arm64 -dylib_install_name @rpath/Storage.framework/Storage -dead_strip -iphoneos_version_min 11.4.0 -syslibroot /Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/Developer/SDKs/iPhoneOS13.2.sdk -ObjC -o /Users/michael/Library/Developer/Xcode/DerivedData/Client-dkalajufptimzyddhrhucemvjmmg/Build/Products/Fennec-iphoneos/Storage.framework/Storage -L/Users/michael/Library/Developer/Xcode/DerivedData/Client-dkalajufptimzyddhrhucemvjmmg/Build/Products/Fennec-iphoneos -L/Users/michael/Library/Developer/Xcode/DerivedData/Client-dkalajufptimzyddhrhucemvjmmg/Build/Products/Release-iphoneos -L/Users/michael/projects/firefox-ios/Carthage/Build/iOS/MozillaAppServices.framework -L/Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/lib/swift/iphoneos -L/usr/lib/swift -no_uuid -filelist /Users/michael/Library/Developer/Xcode/DerivedData/Client-dkalajufptimzyddhrhucemvjmmg/Build/Intermediates.noindex/Client.build/Fennec-iphoneos/Storage.build/Objects-normal/arm64/Storage.LinkFileList -rpath /usr/lib/swift -rpath @executable_path/Frameworks -rpath @executable_path/Frameworks -rpath @loader_path/Frameworks -object_path_lto /Users/michael/Library/Developer/Xcode/DerivedData/Client-dkalajufptimzyddhrhucemvjmmg/Build/Intermediates.noindex/Client.build/Fennec-iphoneos/Storage.build/Objects-normal/arm64/Storage_lto.o -export_dynamic -no_deduplicate -add_ast_path /Users/michael/Library/Developer/Xcode/DerivedData/Client-dkalajufptimzyddhrhucemvjmmg/Build/Intermediates.noindex/Client.build/Fennec-iphoneos/Storage.build/Objects-normal/arm64/Storage.swiftmodule -lxml2 -framework Shared -framework XCGLogger -framework ObjcExceptionBridging -framework MozillaAppServices -framework Fuzi -framework MozillaAppServices -framework SDWebImage -framework SwiftyJSON -dependency_info /Users/michael/Library/Developer/Xcode/DerivedData/Client-dkalajufptimzyddhrhucemvjmmg/Build/Intermediates.noindex/Client.build/Fennec-iphoneos/Storage.build/Objects-normal/arm64/Storage_dependency_info.dat -framework Foundation -lobjc -lSystem /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/lib/clang/11.0.0/lib/darwin/libclang_rt.ios.a -F/Users/michael/Library/Developer/Xcode/DerivedData/Client-dkalajufptimzyddhrhucemvjmmg/Build/Products/Fennec-iphoneos -F/Users/michael/projects/firefox-ios/Carthage/Build/iOS -F/Users/michael/Library/Developer/Xcode/DerivedData/Client-dkalajufptimzyddhrhucemvjmmg/Build/Products/Release-iphoneos -F/Users/michael/projects/application-services/Carthage/Build/iOS/Static