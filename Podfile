target 'sampleapp-ios-swift' do
  use_frameworks!

  pod 'AppCenter'
  pod 'AppCenter/Analytics'
  pod 'AppCenter/Crashes'

  target 'sampleapp-ios-swiftUITests' do
    inherit! :search_paths
    # Pods for testing
    pod 'VSMobileCenterExtensions'
  end

end

post_install do |installer|
        installer.pods_project.build_configurations.each do |config|
            config.build_settings['CODE_SIGNING_REQUIRED'] = "NO"
            config.build_settings['CODE_SIGNING_ALLOWED'] = "NO"
        end
end

