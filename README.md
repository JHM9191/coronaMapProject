# coronaMapProject

- 2020년도 코로나19 사태가 두드러짐에 따라 코로나 확진자에 대한 정보 및 접근 시 알림을 보내는 기능을 탑재한 안드로이드 어플을 개발하였습니다.






## 기능

1. 전체 확진자 이동 경로를 지도에 표시하는 기능
2. 각 확진자의 이동 경로를 지도에 표시하는 기능
3. 총 확진자 인원수, 사망인원수 등 각 나라별 통계 수치를 표시하는 기능
4. 전방 1키로 이내에 접근시 status bar에 notification을 띄우는 기능
5. 국내에 새로운 확진자가 발생할 때 FCM(Firebase Cloud Messaging)을 통해 notification 보내기 기능






## Note

- The API key of google map is secretized as it is a private information. 






## 파일 디렉토리 구성도
- updated date: 20/03/05 21:00


```
├── app
│   ├── build
│   │   ├── generated
│   │   │   ├── ap_generated_sources
│   │   │   │   └── debug
│   │   │   │       └── out
│   │   │   ├── not_namespaced_r_class_sources
│   │   │   │   └── debug
│   │   │   │       └── r
│   │   │   │           ├── androidx
│   │   │   │           │   ├── activity
│   │   │   │           │   ├── appcompat
│   │   │   │           │   │   └── resources
│   │   │   │           │   ├── arch
│   │   │   │           │   │   └── core
│   │   │   │           │   ├── constraintlayout
│   │   │   │           │   │   └── widget
│   │   │   │           │   ├── core
│   │   │   │           │   ├── cursoradapter
│   │   │   │           │   ├── customview
│   │   │   │           │   ├── documentfile
│   │   │   │           │   ├── drawerlayout
│   │   │   │           │   ├── fragment
│   │   │   │           │   ├── interpolator
│   │   │   │           │   ├── legacy
│   │   │   │           │   │   └── coreutils
│   │   │   │           │   ├── lifecycle
│   │   │   │           │   │   ├── livedata
│   │   │   │           │   │   │   └── core
│   │   │   │           │   │   └── viewmodel
│   │   │   │           │   ├── loader
│   │   │   │           │   ├── localbroadcastmanager
│   │   │   │           │   ├── print
│   │   │   │           │   ├── savedstate
│   │   │   │           │   ├── vectordrawable
│   │   │   │           │   │   └── animated
│   │   │   │           │   ├── versionedparcelable
│   │   │   │           │   └── viewpager
│   │   │   │           └── com
│   │   │   │               ├── example
│   │   │   │               │   └── coronaMapProject
│   │   │   │               └── google
│   │   │   │                   ├── android
│   │   │   │                   │   └── gms
│   │   │   │                   │       ├── ads_identifier
│   │   │   │                   │       ├── base
│   │   │   │                   │       ├── common
│   │   │   │                   │       ├── maps
│   │   │   │                   │       ├── measurement
│   │   │   │                   │       │   ├── api
│   │   │   │                   │       │   └── sdk
│   │   │   │                   │       │       └── api
│   │   │   │                   │       ├── measurement_base
│   │   │   │                   │       ├── stats
│   │   │   │                   │       └── tasks
│   │   │   │                   └── firebase
│   │   │   │                       ├── analytics
│   │   │   │                       │   └── connector
│   │   │   │                       ├── firebase_analytics
│   │   │   │                       ├── firebase_core
│   │   │   │                       ├── iid
│   │   │   │                       │   └── internal
│   │   │   │                       ├── measurement
│   │   │   │                       ├── measurement_impl
│   │   │   │                       └── messaging
│   │   │   ├── res
│   │   │   │   ├── google-services
│   │   │   │   │   └── debug
│   │   │   │   │       └── values
│   │   │   │   ├── pngs
│   │   │   │   │   └── debug
│   │   │   │   └── resValues
│   │   │   │       └── debug
│   │   │   └── source
│   │   │       └── buildConfig
│   │   │           ├── androidTest
│   │   │           │   └── debug
│   │   │           │       └── com
│   │   │           │           └── example
│   │   │           │               └── coronaMapProject
│   │   │           │                   └── test
│   │   │           └── debug
│   │   │               └── com
│   │   │                   └── example
│   │   │                       └── coronaMapProject
│   │   ├── intermediates
│   │   │   ├── annotation_processor_list
│   │   │   │   └── debug
│   │   │   ├── apk_list
│   │   │   │   └── debug
│   │   │   │       └── mainApkListPersistenceDebug
│   │   │   ├── blame
│   │   │   │   └── res
│   │   │   │       └── debug
│   │   │   │           ├── multi-v2
│   │   │   │           └── single
│   │   │   ├── bundle_manifest
│   │   │   │   └── debug
│   │   │   │       └── processDebugManifest
│   │   │   │           └── bundle-manifest
│   │   │   ├── check_manifest_result
│   │   │   │   └── debug
│   │   │   │       └── checkDebugManifest
│   │   │   │           └── out
│   │   │   ├── compatible_screen_manifest
│   │   │   │   └── debug
│   │   │   │       └── createDebugCompatibleScreenManifests
│   │   │   │           └── out
│   │   │   ├── dex
│   │   │   │   └── debug
│   │   │   │       ├── mergeExtDexDebug
│   │   │   │       │   └── out
│   │   │   │       ├── mergeLibDexDebug
│   │   │   │       │   └── out
│   │   │   │       └── mergeProjectDexDebug
│   │   │   │           └── out
│   │   │   ├── duplicate_classes_check
│   │   │   │   └── debug
│   │   │   │       └── out
│   │   │   ├── incremental
│   │   │   │   ├── debug-mergeJavaRes
│   │   │   │   │   └── zip-cache
│   │   │   │   ├── debug-mergeNativeLibs
│   │   │   │   │   └── zip-cache
│   │   │   │   ├── mergeDebugAssets
│   │   │   │   ├── mergeDebugJniLibFolders
│   │   │   │   ├── mergeDebugResources
│   │   │   │   │   ├── merged.dir
│   │   │   │   │   │   ├── values
│   │   │   │   │   │   ├── values-af
│   │   │   │   │   │   ├── values-am
│   │   │   │   │   │   ├── values-ar
│   │   │   │   │   │   ├── values-as
│   │   │   │   │   │   ├── values-az
│   │   │   │   │   │   ├── values-b+sr+Latn
│   │   │   │   │   │   ├── values-be
│   │   │   │   │   │   ├── values-bg
│   │   │   │   │   │   ├── values-bn
│   │   │   │   │   │   ├── values-bs
│   │   │   │   │   │   ├── values-ca
│   │   │   │   │   │   ├── values-cs
│   │   │   │   │   │   ├── values-da
│   │   │   │   │   │   ├── values-de
│   │   │   │   │   │   ├── values-el
│   │   │   │   │   │   ├── values-en-rAU
│   │   │   │   │   │   ├── values-en-rCA
│   │   │   │   │   │   ├── values-en-rGB
│   │   │   │   │   │   ├── values-en-rIN
│   │   │   │   │   │   ├── values-en-rXC
│   │   │   │   │   │   ├── values-es
│   │   │   │   │   │   ├── values-es-rUS
│   │   │   │   │   │   ├── values-et
│   │   │   │   │   │   ├── values-eu
│   │   │   │   │   │   ├── values-fa
│   │   │   │   │   │   ├── values-fi
│   │   │   │   │   │   ├── values-fr
│   │   │   │   │   │   ├── values-fr-rCA
│   │   │   │   │   │   ├── values-gl
│   │   │   │   │   │   ├── values-gu
│   │   │   │   │   │   ├── values-h720dp-v13
│   │   │   │   │   │   ├── values-hdpi-v4
│   │   │   │   │   │   ├── values-hi
│   │   │   │   │   │   ├── values-hr
│   │   │   │   │   │   ├── values-hu
│   │   │   │   │   │   ├── values-hy
│   │   │   │   │   │   ├── values-in
│   │   │   │   │   │   ├── values-is
│   │   │   │   │   │   ├── values-it
│   │   │   │   │   │   ├── values-iw
│   │   │   │   │   │   ├── values-ja
│   │   │   │   │   │   ├── values-ka
│   │   │   │   │   │   ├── values-kk
│   │   │   │   │   │   ├── values-km
│   │   │   │   │   │   ├── values-kn
│   │   │   │   │   │   ├── values-ko
│   │   │   │   │   │   ├── values-ky
│   │   │   │   │   │   ├── values-land
│   │   │   │   │   │   ├── values-large-v4
│   │   │   │   │   │   ├── values-ldltr-v21
│   │   │   │   │   │   ├── values-lo
│   │   │   │   │   │   ├── values-lt
│   │   │   │   │   │   ├── values-lv
│   │   │   │   │   │   ├── values-mk
│   │   │   │   │   │   ├── values-ml
│   │   │   │   │   │   ├── values-mn
│   │   │   │   │   │   ├── values-mr
│   │   │   │   │   │   ├── values-ms
│   │   │   │   │   │   ├── values-my
│   │   │   │   │   │   ├── values-nb
│   │   │   │   │   │   ├── values-ne
│   │   │   │   │   │   ├── values-night-v8
│   │   │   │   │   │   ├── values-nl
│   │   │   │   │   │   ├── values-or
│   │   │   │   │   │   ├── values-pa
│   │   │   │   │   │   ├── values-pl
│   │   │   │   │   │   ├── values-port
│   │   │   │   │   │   ├── values-pt
│   │   │   │   │   │   ├── values-pt-rBR
│   │   │   │   │   │   ├── values-pt-rPT
│   │   │   │   │   │   ├── values-ro
│   │   │   │   │   │   ├── values-ru
│   │   │   │   │   │   ├── values-si
│   │   │   │   │   │   ├── values-sk
│   │   │   │   │   │   ├── values-sl
│   │   │   │   │   │   ├── values-sq
│   │   │   │   │   │   ├── values-sr
│   │   │   │   │   │   ├── values-sv
│   │   │   │   │   │   ├── values-sw
│   │   │   │   │   │   ├── values-sw600dp-v13
│   │   │   │   │   │   ├── values-ta
│   │   │   │   │   │   ├── values-te
│   │   │   │   │   │   ├── values-th
│   │   │   │   │   │   ├── values-tl
│   │   │   │   │   │   ├── values-tr
│   │   │   │   │   │   ├── values-uk
│   │   │   │   │   │   ├── values-ur
│   │   │   │   │   │   ├── values-uz
│   │   │   │   │   │   ├── values-v16
│   │   │   │   │   │   ├── values-v17
│   │   │   │   │   │   ├── values-v18
│   │   │   │   │   │   ├── values-v21
│   │   │   │   │   │   ├── values-v22
│   │   │   │   │   │   ├── values-v23
│   │   │   │   │   │   ├── values-v24
│   │   │   │   │   │   ├── values-v25
│   │   │   │   │   │   ├── values-v26
│   │   │   │   │   │   ├── values-v28
│   │   │   │   │   │   ├── values-vi
│   │   │   │   │   │   ├── values-watch-v20
│   │   │   │   │   │   ├── values-watch-v21
│   │   │   │   │   │   ├── values-xlarge-v4
│   │   │   │   │   │   ├── values-zh-rCN
│   │   │   │   │   │   ├── values-zh-rHK
│   │   │   │   │   │   ├── values-zh-rTW
│   │   │   │   │   │   └── values-zu
│   │   │   │   │   └── stripped.dir
│   │   │   │   ├── mergeDebugShaders
│   │   │   │   ├── packageDebug
│   │   │   │   │   └── tmp
│   │   │   │   │       └── debug
│   │   │   │   │           └── zip-cache
│   │   │   │   └── processDebugResources
│   │   │   ├── instant_app_manifest
│   │   │   │   └── debug
│   │   │   ├── javac
│   │   │   │   └── debug
│   │   │   │       └── classes
│   │   │   │           ├── androidx
│   │   │   │           │   ├── activity
│   │   │   │           │   ├── appcompat
│   │   │   │           │   │   └── resources
│   │   │   │           │   ├── arch
│   │   │   │           │   │   └── core
│   │   │   │           │   ├── constraintlayout
│   │   │   │           │   │   └── widget
│   │   │   │           │   ├── core
│   │   │   │           │   ├── cursoradapter
│   │   │   │           │   ├── customview
│   │   │   │           │   ├── documentfile
│   │   │   │           │   ├── drawerlayout
│   │   │   │           │   ├── fragment
│   │   │   │           │   ├── interpolator
│   │   │   │           │   ├── legacy
│   │   │   │           │   │   └── coreutils
│   │   │   │           │   ├── lifecycle
│   │   │   │           │   │   ├── livedata
│   │   │   │           │   │   │   └── core
│   │   │   │           │   │   └── viewmodel
│   │   │   │           │   ├── loader
│   │   │   │           │   ├── localbroadcastmanager
│   │   │   │           │   ├── print
│   │   │   │           │   ├── savedstate
│   │   │   │           │   ├── vectordrawable
│   │   │   │           │   │   └── animated
│   │   │   │           │   ├── versionedparcelable
│   │   │   │           │   └── viewpager
│   │   │   │           └── com
│   │   │   │               ├── example
│   │   │   │               │   └── coronaMapProject
│   │   │   │               └── google
│   │   │   │                   ├── android
│   │   │   │                   │   └── gms
│   │   │   │                   │       ├── ads_identifier
│   │   │   │                   │       ├── base
│   │   │   │                   │       ├── common
│   │   │   │                   │       ├── maps
│   │   │   │                   │       ├── measurement
│   │   │   │                   │       │   ├── api
│   │   │   │                   │       │   └── sdk
│   │   │   │                   │       │       └── api
│   │   │   │                   │       ├── measurement_base
│   │   │   │                   │       ├── stats
│   │   │   │                   │       └── tasks
│   │   │   │                   └── firebase
│   │   │   │                       ├── analytics
│   │   │   │                       │   └── connector
│   │   │   │                       ├── firebase_analytics
│   │   │   │                       ├── firebase_core
│   │   │   │                       ├── iid
│   │   │   │                       │   └── internal
│   │   │   │                       ├── measurement
│   │   │   │                       ├── measurement_impl
│   │   │   │                       └── messaging
│   │   │   ├── lint_jar
│   │   │   │   └── global
│   │   │   │       └── prepareLintJar
│   │   │   ├── lint_publish_jar
│   │   │   │   └── global
│   │   │   │       └── prepareLintJarForPublish
│   │   │   ├── manifest_merge_blame_file
│   │   │   │   ├── debug
│   │   │   │   └── debugAndroidTest
│   │   │   ├── merged_assets
│   │   │   │   └── debug
│   │   │   │       └── out
│   │   │   ├── merged_java_res
│   │   │   │   └── debug
│   │   │   ├── merged_jni_libs
│   │   │   │   └── debug
│   │   │   │       └── out
│   │   │   ├── merged_manifests
│   │   │   │   ├── debug
│   │   │   │   └── debugAndroidTest
│   │   │   ├── merged_native_libs
│   │   │   │   └── debug
│   │   │   │       └── out
│   │   │   ├── merged_shaders
│   │   │   │   └── debug
│   │   │   │       └── out
│   │   │   ├── metadata_feature_manifest
│   │   │   │   └── debug
│   │   │   │       └── processDebugManifest
│   │   │   │           └── metadata-feature
│   │   │   ├── processed_res
│   │   │   │   └── debug
│   │   │   │       └── processDebugResources
│   │   │   │           └── out
│   │   │   ├── res
│   │   │   │   ├── merged
│   │   │   │   │   └── debug
│   │   │   │   └── symbol-table-with-package
│   │   │   │       └── debug
│   │   │   ├── shader_assets
│   │   │   │   └── debug
│   │   │   │       └── compileDebugShaders
│   │   │   │           └── out
│   │   │   ├── signing_config
│   │   │   │   └── debug
│   │   │   │       └── out
│   │   │   ├── stripped_native_libs
│   │   │   │   └── debug
│   │   │   │       └── out
│   │   │   ├── symbols
│   │   │   │   └── debug
│   │   │   ├── tmp
│   │   │   │   └── manifest
│   │   │   │       └── androidTest
│   │   │   │           └── debug
│   │   │   ├── transforms
│   │   │   │   └── dexBuilder
│   │   │   │       └── debug
│   │   │   │           └── 0
│   │   │   │               ├── androidx
│   │   │   │               │   ├── activity
│   │   │   │               │   ├── appcompat
│   │   │   │               │   │   └── resources
│   │   │   │               │   ├── arch
│   │   │   │               │   │   └── core
│   │   │   │               │   ├── constraintlayout
│   │   │   │               │   │   └── widget
│   │   │   │               │   ├── core
│   │   │   │               │   ├── cursoradapter
│   │   │   │               │   ├── customview
│   │   │   │               │   ├── documentfile
│   │   │   │               │   ├── drawerlayout
│   │   │   │               │   ├── fragment
│   │   │   │               │   ├── interpolator
│   │   │   │               │   ├── legacy
│   │   │   │               │   │   └── coreutils
│   │   │   │               │   ├── lifecycle
│   │   │   │               │   │   ├── livedata
│   │   │   │               │   │   │   └── core
│   │   │   │               │   │   └── viewmodel
│   │   │   │               │   ├── loader
│   │   │   │               │   ├── localbroadcastmanager
│   │   │   │               │   ├── print
│   │   │   │               │   ├── savedstate
│   │   │   │               │   ├── vectordrawable
│   │   │   │               │   │   └── animated
│   │   │   │               │   ├── versionedparcelable
│   │   │   │               │   └── viewpager
│   │   │   │               └── com
│   │   │   │                   ├── example
│   │   │   │                   │   └── coronaMapProject
│   │   │   │                   └── google
│   │   │   │                       ├── android
│   │   │   │                       │   └── gms
│   │   │   │                       │       ├── ads_identifier
│   │   │   │                       │       ├── base
│   │   │   │                       │       ├── common
│   │   │   │                       │       ├── maps
│   │   │   │                       │       ├── measurement
│   │   │   │                       │       │   ├── api
│   │   │   │                       │       │   └── sdk
│   │   │   │                       │       │       └── api
│   │   │   │                       │       ├── measurement_base
│   │   │   │                       │       ├── stats
│   │   │   │                       │       └── tasks
│   │   │   │                       └── firebase
│   │   │   │                           ├── analytics
│   │   │   │                           │   └── connector
│   │   │   │                           ├── firebase_analytics
│   │   │   │                           ├── firebase_core
│   │   │   │                           ├── iid
│   │   │   │                           │   └── internal
│   │   │   │                           ├── measurement
│   │   │   │                           ├── measurement_impl
│   │   │   │                           └── messaging
│   │   │   └── validate_signing_config
│   │   │       └── debug
│   │   │           └── out
│   │   ├── outputs
│   │   │   ├── apk
│   │   │   │   └── debug
│   │   │   └── logs
│   │   └── tmp
│   │       └── compileDebugJavaWithJavac
│   ├── libs
│   └── src
│       ├── androidTest
│       │   └── java
│       │       └── com
│       │           └── example
│       │               └── coronaMapProject
│       ├── debug
│       │   └── res
│       │       └── values
│       ├── main
│       │   ├── java
│       │   │   └── com
│       │   │       └── example
│       │   │           └── coronaMapProject
│       │   └── res
│       │       ├── drawable
│       │       ├── drawable-v24
│       │       ├── layout
│       │       ├── mipmap-anydpi-v26
│       │       ├── mipmap-hdpi
│       │       ├── mipmap-mdpi
│       │       ├── mipmap-xhdpi
│       │       ├── mipmap-xxhdpi
│       │       ├── mipmap-xxxhdpi
│       │       ├── raw
│       │       └── values
│       ├── release
│       │   └── res
│       │       └── values
│       └── test
│           └── java
│               └── com
│                   └── example
│                       └── coronaMapProject
└── gradle
    └── wrapper