# -*- coding: utf-8 -*-
$:.unshift("/Library/RubyMotion/lib")
$:.unshift("~/.rubymotion/rubymotion-templates")

# ===========================================================================================
# 1. Be sure to read `readme.md`.
# ===========================================================================================

require 'motion/project/template/ios'

begin
  require 'bundler'
  Bundler.require
rescue LoadError
end

Motion::Project::App.setup do |app|
  # Use `rake config' to see complete project settings.
  define_icon_defaults!(app)

  # ===========================================================================================
  # 2. Set your app name (this is what will show up under the icon when your app is installed).
  # ===========================================================================================
  app.name = 'firestore-rubymotion'

  # version for your app
  app.version = '1.0'

  app.deployment_target = "10.3"
  app.sdk_version = "11.3"

  # ===========================================================================================
  # 3. Set your deployment target (it's recommended that you at least target 10.0 and above).
  #    If you're using RubyMotion Starter Edition. You cannot set this value (the latest
  #    version of iOS will be used).
  # ===========================================================================================
  # app.deployment_target = '10.0'

  # ===========================================================================================
  # 4. Your app identifier is needed to deploy to an actual device. You do not need to set this
  #    if you are using the simulator. You can create an app identifier at:
  #    https://developer.apple.com/account/ios/identifier/bundle. You must enroll into Apple's
  #    Developer program to get access to this screen (there is an annual fee of $99).
  # ===========================================================================================
  # app.identifier = ''

  # ===========================================================================================
  # 5. If you need to reference any additional iOS libraries, use the config array below.
  # ===========================================================================================
  # app.frameworks << "StoreKit"

  # reasonable defaults
  app.device_family = [:iphone, :ipad]
  app.interface_orientations = [:portrait]
  app.info_plist['UIRequiresFullScreen'] = true
  app.info_plist['ITSAppUsesNonExemptEncryption'] = false

  # ===========================================================================================
  # 6. To deploy to an actual device, you will need to create a developer certificate at:
  #    https://developer.apple.com/account/ios/certificate/development
  #    The name of the certificate will be accessible via Keychain Access. Set the value you
  #    see there below.
  # ===========================================================================================
  # app.codesign_certificate = ''

  # ===========================================================================================
  # 7. To deploy to an actual device, you will need to create a provisioning profile. First:
  #    register your device at:
  #    https://developer.apple.com/account/ios/device/
  #
  #    Then create a development provisioning profile at:
  #    https://developer.apple.com/account/ios/profile/limited
  #
  #    Download the profile and set the path to the download location below.
  # ===========================================================================================
  # app.provisioning_profile = ''

  # ===========================================================================================
  # 8. Similar to Step 7. Production, create a production certificate at:
  #    https://developer.apple.com/account/ios/certificate/distribution.
  #    These values will need to be set to before you can deploy to the App Store. Compile
  #    using `rake clean archive:distribution` and upload the .ipa under ./build using
  #    Application Loader.
  # ===========================================================================================
  # app.codesign_certificate = ''
  # app.provisioning_profile = ''

  # ===========================================================================================
  # 9. If you want to create a beta build. Uncomment the line below and set your profile to
  #    point to your production provisions (Step 8).
  # ===========================================================================================
  # app.entitlements['beta-reports-active'] = true

  app.frameworks += ['SafariServices']
  app.libs += ['/usr/lib/libsqlite3.dylib']

  # General libs
  app.vendor_project('vendor/Firebase/Analytics/nanopb.framework', :static, :products => ['nanopb'], :headers_dir => 'Headers')  
  app.vendor_project('vendor/Firebase/Firestore/BoringSSL.framework', :static, :products => ['BoringSSL'], :headers_dir => 'Headers')  
  app.vendor_project('vendor/Firebase/Firestore/Protobuf.framework', :static, :products => ['Protobuf'], :headers_dir => 'Headers')  
  app.vendor_project('vendor/Firebase/Firestore/gRPC-Core.framework', :static, :products => ['gRPC-Core'], :headers_dir => 'Headers')  
  app.vendor_project('vendor/Firebase/Firestore/gRPC-RxLibrary.framework', :static, :products => ['gRPC-RxLibrary'], :headers_dir => 'Headers')  
  app.vendor_project('vendor/Firebase/Firestore/gRPC.framework', :static, :products => ['gRPC'], :headers_dir => 'Headers')  
  app.vendor_project('vendor/Firebase/Firestore/gRPC-RxLibrary.framework', :static, :products => ['gRPC-RxLibrary'], :headers_dir => 'Headers')  
  app.vendor_project('vendor/Firebase/Firestore/gRPC-ProtoRPC.framework', :static, :products => ['gRPC-ProtoRPC'], :headers_dir => 'Headers')  

  # Analytics
  app.vendor_project('vendor/Firebase/Analytics/FirebaseCore.framework', :static, :products => ['FirebaseCore'], :headers_dir => 'Headers')  
  app.vendor_project('vendor/Firebase/Analytics/FirebaseNanoPB.framework', :static, :products => ['FirebaseNanoPB'])  
  app.vendor_project('vendor/Firebase/Analytics/FirebaseCoreDiagnostics.framework', :static, :products => ['FirebaseCoreDiagnostics'])  
  app.vendor_project('vendor/Firebase/Analytics/FirebaseInstanceID.framework', :static, :products => ['FirebaseInstanceID'], :headers_dir => 'Headers')  
  app.vendor_project('vendor/Firebase/Analytics/GoogleToolboxForMac.framework', :static, :products => ['GoogleToolboxForMac'], :headers_dir => 'Headers')  
  app.vendor_project('vendor/Firebase/Analytics/FirebaseAnalytics.framework', :static, :products => ['FirebaseAnalytics'], :headers_dir => 'Headers')  

  # Auth
  app.vendor_project('vendor/Firebase/Auth/FirebaseAuth.framework', :static, :products => ['FirebaseAuth'], :headers_dir => 'Headers')  
  app.vendor_project('vendor/Firebase/Auth/GTMSessionFetcher.framework', :static, :products => ['GTMSessionFetcher'], :headers_dir => 'Headers')  

  # Database
  app.vendor_project('vendor/Firebase/Database/leveldb-library.framework', :static, :products => ['leveldb-library'], :headers_dir => 'Headers')  
  app.vendor_project('vendor/Firebase/Database/FirebaseDatabase.framework', :static, :products => ['FirebaseDatabase'], :headers_dir => 'Headers')  

  # Firestore
  app.vendor_project('vendor/Firebase/Firestore/FirebaseFirestore.framework', :static, :products => ['FirebaseFirestore'], :headers_dir => 'Headers')  


end

def define_icon_defaults!(app)
  # This is required as of iOS 11.0 (you must use asset catalogs to
  # define icons or your app will be rejected. More information in
  # located in the readme.

  app.info_plist['CFBundleIcons'] = {
    'CFBundlePrimaryIcon' => {
      'CFBundleIconName' => 'AppIcon',
      'CFBundleIconFiles' => ['AppIcon60x60']
    }
  }

  app.info_plist['CFBundleIcons~ipad'] = {
    'CFBundlePrimaryIcon' => {
      'CFBundleIconName' => 'AppIcon',
      'CFBundleIconFiles' => ['AppIcon60x60', 'AppIcon76x76']
    }
  }
end
