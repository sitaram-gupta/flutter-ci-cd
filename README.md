# semaphore_flutter

# CI/CD fastlane app distribution
# Commands available below:
flutter create semaphore_flutter --org com.companyname <br/>
flutter build apk --release <br/>
open build/app/outputs/flutter-apk/ <br/>
cd android <br/>
fastlane init <br/>
fastlane add_plugin firebase_app_distribution <br/>
firebase login:ci <br/>
fastlane deploy

# code to replace to Fasfile
```default_platform(:android)

platform :android do
  desc "Deploy to firebase"
  lane :deploy do
   begin
    # start Add this
    firebase_app_distribution(
      groups: "Alpha",
      release_notes: "Improvements and Bug Fixes",
      apk_path: "../build/app/outputs/flutter-apk/app-release.apk",
      firebase_cli_path: "/usr/local/bin/firebase",
      firebase_cli_token: "1//0gd15jjaqFPy7CgYIARAAGBASNwF-L9Irw34GXqWBslYpaDfLdKGdhMyILcVQd5_avocpdzwGscJxS63HAcHVDEITB9nS2XRUcZc",
      app: "1:103797579986:android:57e38f70a220e84ed98d0b",
    )
    # end
    end
  end
end
```
