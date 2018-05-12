# Steps to getting Firebase/Firestore working with iOS 11.3 and 10.3

1. Download the Firebase static frameworks here:
[https://firebase.google.com/docs/ios/setup#frameworks](https://firebase.google.com/docs/ios/setup#frameworks)
2. Unzip and copy them over to your ```/vendor```
3. Copy ```gRPCCertificates.bundle``` from ```/vendor/Firebase/Firestore/Resources``` to your ```/resources```
4. Update your Rakefile with:
```ruby
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
```

5. Test that it compiles ```rake``` or ```rake target=10.3.1```