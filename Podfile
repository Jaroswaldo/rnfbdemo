# Uncomment the next line to define a global platform for your project
platform :ios, '9.0'

target 'rnfbdemo' do
  # Comment the next line if you don't want to use dynamic frameworks
  use_frameworks!

  # Pods for rnfbdemo
  #pod 'React', :path => '../node_modules/react-native', :subspecs => [
  #  'Core',
  #  'CxxBridge', # Include this for RN >= 0.47
  #  'DevSupport', # Include this to enable In-App Devmenu if RN >= 0.43
  #  'RCTText',
  #  'RCTNetwork',
  #  'RCTWebSocket', # Needed for debugging
  #  'RCTAnimation', # Needed for FlatList and animations running on native UI thread
    # Add any other subspecs you want to use in your project
  #]

  # Explicitly include Yoga if you are using RN >= 0.42.0
  #pod 'yoga', :path => '../node_modules/react-native/ReactCommon/yoga'

  # Third party deps podspec link
  #pod 'DoubleConversion', :podspec => '../node_modules/react-native/third-party-podspecs/DoubleConversion.podspec'
  #pod 'glog', :podspec => '../node_modules/react-native/third-party-podspecs/glog.podspec'
  #pod 'Folly', :podspec => '../node_modules/react-native/third-party-podspecs/Folly.podspec'

  # Required by RNFirebase
  pod 'Firebase/Core', '~> 5.20.2'

  # [OPTIONAL PODS] - comment out pods for firebase products you won't be using.
  #pod 'GoogleIDFASupport', '~> 3.14.0'
  #pod 'Firebase/AdMob', '~> 5.20.2'
  #pod 'Firebase/Auth', '~> 5.20.2'
  #pod 'Firebase/Database', '~> 5.20.2'
  #pod 'Firebase/Functions', '~> 5.20.2'
  #pod 'Firebase/DynamicLinks', '~> 5.20.2'
  #pod 'Firebase/Firestore', '~> 5.20.2'
  #pod 'Firebase/Invites', '~> 5.20.2'
  #pod 'Firebase/Messaging', '~> 5.20.2'
  #pod 'Firebase/RemoteConfig', '~> 5.20.2'
  #pod 'Firebase/Storage', '~> 5.20.2'
  #pod 'Firebase/Performance', '~> 5.20.2'
  #pod 'Fabric', '~> 1.10.0'
  #pod 'Crashlytics', '~> 3.13.0'

  #pod 'Firebase/MLVision', '~> 5.20.2'
  #pod 'Firebase/MLVisionLabelModel', '~> 5.20.2'
  #pod 'Firebase/MLVisionBarcodeModel', '~> 5.20.2'
  #pod 'Firebase/MLVisionTextModel', '~> 5.20.2'
  #pod 'Firebase/MLVisionFaceModel', '~> 5.20.2'

  target 'rnfbdemoTests' do
    inherit! :search_paths
    # Pods for testing
  end

end

target 'rnfbdemo-tvOS' do
  # Comment the next line if you don't want to use dynamic frameworks
  use_frameworks!

  # Pods for rnfbdemo-tvOS

  target 'rnfbdemo-tvOSTests' do
    inherit! :search_paths
    # Pods for testing
  end

end

# React-Native is not great about React double-including from the Podfile
post_install do |installer|
#  installer.pods_project.targets.each do |target|
#    if target.name == "React"
#      target.remove_from_project
#    end

    # The following is needed to ensure the "archive" step works in XCode.
    # It removes React & Yoga from the Pods project, as it is already included in the main project.
    # Without this, you'd see errors when you archive like:
    # "Multiple commands produce ... libReact.a"
    # "Multiple commands produce ... libyoga.a"
    # FIXME real fix is like so: https://stackoverflow.com/a/55328241/9910298 (remove duplicate refs)
#    targets_to_ignore = %w(React yoga)
#    if targets_to_ignore.include? target.name
#      target.remove_from_project
#    end
#  end
  system("mkdir -p Pods/Headers/Public/FirebaseCore && cp Pods/FirebaseCore/Firebase/Core/Public/* Pods/Headers/Public/FirebaseCore/")
end