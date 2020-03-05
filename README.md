# coronaMapProject(개발중)

- 2020년도 코로나19 사태가 두드러짐에 따라 코로나 확진자에 대한 정보 및 접근 시 알림을 보내는 기능을 탑재한 안드로이드 어플을 개발하였습니다.





> 국내 코로나19 현황
>
> > ![국내_코로나19_현황](.img/corona.jpg)
> >
> > 출처: [연합뉴스](https://www.yna.co.kr/view/GYH20200304001000044)
>
> 2020년 4월 3일 (수) 기준 질병관리본부, 중앙방역대책본부에서 보도한 코로나19 현황을 요약한 그림입니다.









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
├── README.md
├── app
│   ├── app.iml
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
│   │   │   │           │   │   └── R.java
│   │   │   │           │   ├── appcompat
│   │   │   │           │   │   ├── R.java
│   │   │   │           │   │   └── resources
│   │   │   │           │   │       └── R.java
│   │   │   │           │   ├── arch
│   │   │   │           │   │   └── core
│   │   │   │           │   │       └── R.java
│   │   │   │           │   ├── constraintlayout
│   │   │   │           │   │   └── widget
│   │   │   │           │   │       └── R.java
│   │   │   │           │   ├── core
│   │   │   │           │   │   └── R.java
│   │   │   │           │   ├── cursoradapter
│   │   │   │           │   │   └── R.java
│   │   │   │           │   ├── customview
│   │   │   │           │   │   └── R.java
│   │   │   │           │   ├── documentfile
│   │   │   │           │   │   └── R.java
│   │   │   │           │   ├── drawerlayout
│   │   │   │           │   │   └── R.java
│   │   │   │           │   ├── fragment
│   │   │   │           │   │   └── R.java
│   │   │   │           │   ├── interpolator
│   │   │   │           │   │   └── R.java
│   │   │   │           │   ├── legacy
│   │   │   │           │   │   └── coreutils
│   │   │   │           │   │       └── R.java
│   │   │   │           │   ├── lifecycle
│   │   │   │           │   │   ├── R.java
│   │   │   │           │   │   ├── livedata
│   │   │   │           │   │   │   ├── R.java
│   │   │   │           │   │   │   └── core
│   │   │   │           │   │   │       └── R.java
│   │   │   │           │   │   └── viewmodel
│   │   │   │           │   │       └── R.java
│   │   │   │           │   ├── loader
│   │   │   │           │   │   └── R.java
│   │   │   │           │   ├── localbroadcastmanager
│   │   │   │           │   │   └── R.java
│   │   │   │           │   ├── print
│   │   │   │           │   │   └── R.java
│   │   │   │           │   ├── savedstate
│   │   │   │           │   │   └── R.java
│   │   │   │           │   ├── vectordrawable
│   │   │   │           │   │   ├── R.java
│   │   │   │           │   │   └── animated
│   │   │   │           │   │       └── R.java
│   │   │   │           │   ├── versionedparcelable
│   │   │   │           │   │   └── R.java
│   │   │   │           │   └── viewpager
│   │   │   │           │       └── R.java
│   │   │   │           └── com
│   │   │   │               ├── example
│   │   │   │               │   └── coronaMapProject
│   │   │   │               │       └── R.java
│   │   │   │               └── google
│   │   │   │                   ├── android
│   │   │   │                   │   └── gms
│   │   │   │                   │       ├── ads_identifier
│   │   │   │                   │       │   └── R.java
│   │   │   │                   │       ├── base
│   │   │   │                   │       │   └── R.java
│   │   │   │                   │       ├── common
│   │   │   │                   │       │   └── R.java
│   │   │   │                   │       ├── maps
│   │   │   │                   │       │   └── R.java
│   │   │   │                   │       ├── measurement
│   │   │   │                   │       │   ├── api
│   │   │   │                   │       │   │   └── R.java
│   │   │   │                   │       │   └── sdk
│   │   │   │                   │       │       ├── R.java
│   │   │   │                   │       │       └── api
│   │   │   │                   │       │           └── R.java
│   │   │   │                   │       ├── measurement_base
│   │   │   │                   │       │   └── R.java
│   │   │   │                   │       ├── stats
│   │   │   │                   │       │   └── R.java
│   │   │   │                   │       └── tasks
│   │   │   │                   │           └── R.java
│   │   │   │                   └── firebase
│   │   │   │                       ├── R.java
│   │   │   │                       ├── analytics
│   │   │   │                       │   └── connector
│   │   │   │                       │       └── R.java
│   │   │   │                       ├── firebase_analytics
│   │   │   │                       │   └── R.java
│   │   │   │                       ├── firebase_core
│   │   │   │                       │   └── R.java
│   │   │   │                       ├── iid
│   │   │   │                       │   ├── R.java
│   │   │   │                       │   └── internal
│   │   │   │                       │       └── R.java
│   │   │   │                       ├── measurement
│   │   │   │                       │   └── R.java
│   │   │   │                       ├── measurement_impl
│   │   │   │                       │   └── R.java
│   │   │   │                       └── messaging
│   │   │   │                           └── R.java
│   │   │   ├── res
│   │   │   │   ├── google-services
│   │   │   │   │   └── debug
│   │   │   │   │       └── values
│   │   │   │   │           └── values.xml
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
│   │   │           │                       └── BuildConfig.java
│   │   │           └── debug
│   │   │               └── com
│   │   │                   └── example
│   │   │                       └── coronaMapProject
│   │   │                           └── BuildConfig.java
│   │   ├── intermediates
│   │   │   ├── annotation_processor_list
│   │   │   │   └── debug
│   │   │   │       └── annotationProcessors.json
│   │   │   ├── apk_list
│   │   │   │   └── debug
│   │   │   │       └── mainApkListPersistenceDebug
│   │   │   │           └── apk-list.gson
│   │   │   ├── blame
│   │   │   │   └── res
│   │   │   │       └── debug
│   │   │   │           ├── multi-v2
│   │   │   │           │   ├── debug.json
│   │   │   │           │   ├── values-af.json
│   │   │   │           │   ├── values-am.json
│   │   │   │           │   ├── values-ar.json
│   │   │   │           │   ├── values-as.json
│   │   │   │           │   ├── values-az.json
│   │   │   │           │   ├── values-b+sr+Latn.json
│   │   │   │           │   ├── values-be.json
│   │   │   │           │   ├── values-bg.json
│   │   │   │           │   ├── values-bn.json
│   │   │   │           │   ├── values-bs.json
│   │   │   │           │   ├── values-ca.json
│   │   │   │           │   ├── values-cs.json
│   │   │   │           │   ├── values-da.json
│   │   │   │           │   ├── values-de.json
│   │   │   │           │   ├── values-el.json
│   │   │   │           │   ├── values-en-rAU.json
│   │   │   │           │   ├── values-en-rCA.json
│   │   │   │           │   ├── values-en-rGB.json
│   │   │   │           │   ├── values-en-rIN.json
│   │   │   │           │   ├── values-en-rXC.json
│   │   │   │           │   ├── values-es-rUS.json
│   │   │   │           │   ├── values-es.json
│   │   │   │           │   ├── values-et.json
│   │   │   │           │   ├── values-eu.json
│   │   │   │           │   ├── values-fa.json
│   │   │   │           │   ├── values-fi.json
│   │   │   │           │   ├── values-fr-rCA.json
│   │   │   │           │   ├── values-fr.json
│   │   │   │           │   ├── values-gl.json
│   │   │   │           │   ├── values-gu.json
│   │   │   │           │   ├── values-h720dp-v13.json
│   │   │   │           │   ├── values-hdpi-v4.json
│   │   │   │           │   ├── values-hi.json
│   │   │   │           │   ├── values-hr.json
│   │   │   │           │   ├── values-hu.json
│   │   │   │           │   ├── values-hy.json
│   │   │   │           │   ├── values-in.json
│   │   │   │           │   ├── values-is.json
│   │   │   │           │   ├── values-it.json
│   │   │   │           │   ├── values-iw.json
│   │   │   │           │   ├── values-ja.json
│   │   │   │           │   ├── values-ka.json
│   │   │   │           │   ├── values-kk.json
│   │   │   │           │   ├── values-km.json
│   │   │   │           │   ├── values-kn.json
│   │   │   │           │   ├── values-ko.json
│   │   │   │           │   ├── values-ky.json
│   │   │   │           │   ├── values-land.json
│   │   │   │           │   ├── values-large-v4.json
│   │   │   │           │   ├── values-ldltr-v21.json
│   │   │   │           │   ├── values-lo.json
│   │   │   │           │   ├── values-lt.json
│   │   │   │           │   ├── values-lv.json
│   │   │   │           │   ├── values-mk.json
│   │   │   │           │   ├── values-ml.json
│   │   │   │           │   ├── values-mn.json
│   │   │   │           │   ├── values-mr.json
│   │   │   │           │   ├── values-ms.json
│   │   │   │           │   ├── values-my.json
│   │   │   │           │   ├── values-nb.json
│   │   │   │           │   ├── values-ne.json
│   │   │   │           │   ├── values-night-v8.json
│   │   │   │           │   ├── values-nl.json
│   │   │   │           │   ├── values-or.json
│   │   │   │           │   ├── values-pa.json
│   │   │   │           │   ├── values-pl.json
│   │   │   │           │   ├── values-port.json
│   │   │   │           │   ├── values-pt-rBR.json
│   │   │   │           │   ├── values-pt-rPT.json
│   │   │   │           │   ├── values-pt.json
│   │   │   │           │   ├── values-ro.json
│   │   │   │           │   ├── values-ru.json
│   │   │   │           │   ├── values-si.json
│   │   │   │           │   ├── values-sk.json
│   │   │   │           │   ├── values-sl.json
│   │   │   │           │   ├── values-sq.json
│   │   │   │           │   ├── values-sr.json
│   │   │   │           │   ├── values-sv.json
│   │   │   │           │   ├── values-sw.json
│   │   │   │           │   ├── values-sw600dp-v13.json
│   │   │   │           │   ├── values-ta.json
│   │   │   │           │   ├── values-te.json
│   │   │   │           │   ├── values-th.json
│   │   │   │           │   ├── values-tl.json
│   │   │   │           │   ├── values-tr.json
│   │   │   │           │   ├── values-uk.json
│   │   │   │           │   ├── values-ur.json
│   │   │   │           │   ├── values-uz.json
│   │   │   │           │   ├── values-v16.json
│   │   │   │           │   ├── values-v17.json
│   │   │   │           │   ├── values-v18.json
│   │   │   │           │   ├── values-v21.json
│   │   │   │           │   ├── values-v22.json
│   │   │   │           │   ├── values-v23.json
│   │   │   │           │   ├── values-v24.json
│   │   │   │           │   ├── values-v25.json
│   │   │   │           │   ├── values-v26.json
│   │   │   │           │   ├── values-v28.json
│   │   │   │           │   ├── values-vi.json
│   │   │   │           │   ├── values-watch-v20.json
│   │   │   │           │   ├── values-watch-v21.json
│   │   │   │           │   ├── values-xlarge-v4.json
│   │   │   │           │   ├── values-zh-rCN.json
│   │   │   │           │   ├── values-zh-rHK.json
│   │   │   │           │   ├── values-zh-rTW.json
│   │   │   │           │   ├── values-zu.json
│   │   │   │           │   └── values.json
│   │   │   │           └── single
│   │   │   │               └── debug.json
│   │   │   ├── bundle_manifest
│   │   │   │   └── debug
│   │   │   │       └── processDebugManifest
│   │   │   │           └── bundle-manifest
│   │   │   │               ├── AndroidManifest.xml
│   │   │   │               └── output.json
│   │   │   ├── check_manifest_result
│   │   │   │   └── debug
│   │   │   │       └── checkDebugManifest
│   │   │   │           └── out
│   │   │   ├── compatible_screen_manifest
│   │   │   │   └── debug
│   │   │   │       └── createDebugCompatibleScreenManifests
│   │   │   │           └── out
│   │   │   │               └── output.json
│   │   │   ├── dex
│   │   │   │   └── debug
│   │   │   │       ├── mergeExtDexDebug
│   │   │   │       │   └── out
│   │   │   │       │       └── classes.dex
│   │   │   │       ├── mergeLibDexDebug
│   │   │   │       │   └── out
│   │   │   │       └── mergeProjectDexDebug
│   │   │   │           └── out
│   │   │   │               └── classes.dex
│   │   │   ├── duplicate_classes_check
│   │   │   │   └── debug
│   │   │   │       └── out
│   │   │   ├── incremental
│   │   │   │   ├── debug-mergeJavaRes
│   │   │   │   │   ├── merge-state
│   │   │   │   │   └── zip-cache
│   │   │   │   │       ├── 0In4WzX3+ingZ1YfMQVJZEZiEQU=
│   │   │   │   │       ├── 1bcYDu05EN4mg+8S7_DCbL5MQ1w=
│   │   │   │   │       ├── 29jDtashUR5izbFqwiLdGUK8BXY=
│   │   │   │   │       ├── 2Mew1UTeYP3lfTvG+80qG1jYZjo=
│   │   │   │   │       ├── 4zp9n2d2qYaLP6FsMgUh5D0Mixc=
│   │   │   │   │       ├── 5TqY1H9Dq2VeDMdkcc+xeKnymXU=
│   │   │   │   │       ├── 8nqEDWWCU6nlTAkfEjTT6gbuW0k=
│   │   │   │   │       ├── 91htjSy+kpj_6VAlAkkx+FLWlxA=
│   │   │   │   │       ├── 9ArEdhc5Hsj9R1l+LSfXruhhNRA=
│   │   │   │   │       ├── BxQAs_PQntcNPIyL9k54fYfdHZw=
│   │   │   │   │       ├── C79qkp4mzUJ0c8rxylFF2lck72s=
│   │   │   │   │       ├── CBBdUW9sP6PYTVQo_G2WtdCGgfU=
│   │   │   │   │       ├── Fp_7r10SFgPjQXfu4j58LMIJP1g=
│   │   │   │   │       ├── GK_hiYIyatcUBBkG3iYXpW_ck9Q=
│   │   │   │   │       ├── HrkS9KJ1fHBiby_Qk7TjwNJEVwE=
│   │   │   │   │       ├── IDJgQk8mevQfFhYccaD8yloDioE=
│   │   │   │   │       ├── Ivvl6jaJ9Au6foEprD_BWmv1vyU=
│   │   │   │   │       ├── Ka0nAEJ9V+HYjvn1kZa6TGocK+E=
│   │   │   │   │       ├── M9SN8VhXRLomoKuX4hLPIomj1l4=
│   │   │   │   │       ├── Ng9tpRsGxgPFHRZrIjYSFHAcfAg=
│   │   │   │   │       ├── OJ27oYwKeKTI_c9d7Ef7OhrWbns=
│   │   │   │   │       ├── PfK0l8DAfb7+AtNuzmr4PMmW2+c=
│   │   │   │   │       ├── Pgl0MN00FPu_K1bfAJm17vcyZy4=
│   │   │   │   │       ├── Q51lUxaUiU+RbR+NWiQbOj_10ok=
│   │   │   │   │       ├── QO44tL+ZGkWGXOThf4es3A876vs=
│   │   │   │   │       ├── RDKQoLWYEJyNTpEMfJNq0UtivoU=
│   │   │   │   │       ├── RP9qMfW8wlv0KQqL9lTRJhp7cfU=
│   │   │   │   │       ├── S27Coijs4mcfAuDTtJBA_I2mQ+8=
│   │   │   │   │       ├── SIWAom17yMuC_S6XhMClOcJaN2Q=
│   │   │   │   │       ├── UHmLw9FDk6ptNNtwlZ0j99Ddjyk=
│   │   │   │   │       ├── VJQJ2IA0hXrPI7WKmKGr6vC29V8=
│   │   │   │   │       ├── VzPxaTal29q0lu+iKX1Zb5m3kI0=
│   │   │   │   │       ├── Wh3pvGff_JrdxIT1q9k+fX7yzro=
│   │   │   │   │       ├── X+R+akldS0qvDwwBvXdMBzT8wIw=
│   │   │   │   │       ├── XFgx4cjghBGmMKBMUjgfewTOa+M=
│   │   │   │   │       ├── YckDejC9oQVWMajWMBtjE8rqyK0=
│   │   │   │   │       ├── Z781+mhDy2jCobzlQpQTrrY6A1E=
│   │   │   │   │       ├── ZAqlEFX3geM3lZQLCKvFVq6IPTA=
│   │   │   │   │       ├── ZL2YrhsqAx3wYQzgdTt5ImiWiSc=
│   │   │   │   │       ├── _EMRmcJHyZFLTJnrMfv5dA1TyTE=
│   │   │   │   │       ├── bEy4sAqV_8pnZF5rX7YYrPVfrVA=
│   │   │   │   │       ├── bRQqqlq8Q4VwVrijmAn1RX6T24M=
│   │   │   │   │       ├── bjDcLC2IZjoVWNitU8tjGY1lO4Q=
│   │   │   │   │       ├── c+6QaR4E24CbIjilFHiqH6PJPb8=
│   │   │   │   │       ├── fDrvBwazEqwezTJaFVuRfo5lCWU=
│   │   │   │   │       ├── fqbjhNolEHyqugYTT+lDbRF+rPQ=
│   │   │   │   │       ├── hA0+PoduGqNYxbr5w5Pjr+5dguA=
│   │   │   │   │       ├── hazQ60DO5s0T4XEiwqKaoS8U75w=
│   │   │   │   │       ├── iHX_4py8xdOpQSNjuhp+i4RpNJA=
│   │   │   │   │       ├── jIEFQVBi1zmy33kCwCz1ga6lDQg=
│   │   │   │   │       ├── kFQZwetldMkXHV2s7M8YFIJkhg4=
│   │   │   │   │       ├── mYQX3vFq5Iqf1SpIEo36EXg70GU=
│   │   │   │   │       ├── mxfAjJW131MyIfQmAmATmuEFa0I=
│   │   │   │   │       ├── nhWD8PlwE0TyacITvlrcG0ltPWU=
│   │   │   │   │       ├── ogS9tTlBeLCtOqFQhy8uwRK6pwM=
│   │   │   │   │       ├── poKr9SdG8KmzBvSL10Umdl8GQjc=
│   │   │   │   │       ├── rzbqj0eiUlMBqFdJfGcJY6K7EZw=
│   │   │   │   │       ├── s4GHHSePhCoQsxWLGGL+ydVJg3I=
│   │   │   │   │       ├── wZVPWZ7C6yjk1512_qlyosUDadY=
│   │   │   │   │       ├── ycIdvI6wJXHDs9dLkn_MM_ba4Ks=
│   │   │   │   │       └── yxyzj0J8Vy3xePnPmegMedH1wqU=
│   │   │   │   ├── debug-mergeNativeLibs
│   │   │   │   │   ├── merge-state
│   │   │   │   │   └── zip-cache
│   │   │   │   │       ├── 0In4WzX3+ingZ1YfMQVJZEZiEQU=
│   │   │   │   │       ├── 1bcYDu05EN4mg+8S7_DCbL5MQ1w=
│   │   │   │   │       ├── 29jDtashUR5izbFqwiLdGUK8BXY=
│   │   │   │   │       ├── 2Mew1UTeYP3lfTvG+80qG1jYZjo=
│   │   │   │   │       ├── 4zp9n2d2qYaLP6FsMgUh5D0Mixc=
│   │   │   │   │       ├── 5TqY1H9Dq2VeDMdkcc+xeKnymXU=
│   │   │   │   │       ├── 8nqEDWWCU6nlTAkfEjTT6gbuW0k=
│   │   │   │   │       ├── 91htjSy+kpj_6VAlAkkx+FLWlxA=
│   │   │   │   │       ├── 9ArEdhc5Hsj9R1l+LSfXruhhNRA=
│   │   │   │   │       ├── BxQAs_PQntcNPIyL9k54fYfdHZw=
│   │   │   │   │       ├── C79qkp4mzUJ0c8rxylFF2lck72s=
│   │   │   │   │       ├── CBBdUW9sP6PYTVQo_G2WtdCGgfU=
│   │   │   │   │       ├── Fp_7r10SFgPjQXfu4j58LMIJP1g=
│   │   │   │   │       ├── GK_hiYIyatcUBBkG3iYXpW_ck9Q=
│   │   │   │   │       ├── HrkS9KJ1fHBiby_Qk7TjwNJEVwE=
│   │   │   │   │       ├── IDJgQk8mevQfFhYccaD8yloDioE=
│   │   │   │   │       ├── Ivvl6jaJ9Au6foEprD_BWmv1vyU=
│   │   │   │   │       ├── Ka0nAEJ9V+HYjvn1kZa6TGocK+E=
│   │   │   │   │       ├── M9SN8VhXRLomoKuX4hLPIomj1l4=
│   │   │   │   │       ├── Ng9tpRsGxgPFHRZrIjYSFHAcfAg=
│   │   │   │   │       ├── OJ27oYwKeKTI_c9d7Ef7OhrWbns=
│   │   │   │   │       ├── PfK0l8DAfb7+AtNuzmr4PMmW2+c=
│   │   │   │   │       ├── Pgl0MN00FPu_K1bfAJm17vcyZy4=
│   │   │   │   │       ├── Q51lUxaUiU+RbR+NWiQbOj_10ok=
│   │   │   │   │       ├── QO44tL+ZGkWGXOThf4es3A876vs=
│   │   │   │   │       ├── RDKQoLWYEJyNTpEMfJNq0UtivoU=
│   │   │   │   │       ├── RP9qMfW8wlv0KQqL9lTRJhp7cfU=
│   │   │   │   │       ├── S27Coijs4mcfAuDTtJBA_I2mQ+8=
│   │   │   │   │       ├── SIWAom17yMuC_S6XhMClOcJaN2Q=
│   │   │   │   │       ├── UHmLw9FDk6ptNNtwlZ0j99Ddjyk=
│   │   │   │   │       ├── VJQJ2IA0hXrPI7WKmKGr6vC29V8=
│   │   │   │   │       ├── VzPxaTal29q0lu+iKX1Zb5m3kI0=
│   │   │   │   │       ├── Wh3pvGff_JrdxIT1q9k+fX7yzro=
│   │   │   │   │       ├── X+R+akldS0qvDwwBvXdMBzT8wIw=
│   │   │   │   │       ├── XFgx4cjghBGmMKBMUjgfewTOa+M=
│   │   │   │   │       ├── YckDejC9oQVWMajWMBtjE8rqyK0=
│   │   │   │   │       ├── Z781+mhDy2jCobzlQpQTrrY6A1E=
│   │   │   │   │       ├── ZAqlEFX3geM3lZQLCKvFVq6IPTA=
│   │   │   │   │       ├── ZL2YrhsqAx3wYQzgdTt5ImiWiSc=
│   │   │   │   │       ├── _EMRmcJHyZFLTJnrMfv5dA1TyTE=
│   │   │   │   │       ├── bEy4sAqV_8pnZF5rX7YYrPVfrVA=
│   │   │   │   │       ├── bRQqqlq8Q4VwVrijmAn1RX6T24M=
│   │   │   │   │       ├── bjDcLC2IZjoVWNitU8tjGY1lO4Q=
│   │   │   │   │       ├── c+6QaR4E24CbIjilFHiqH6PJPb8=
│   │   │   │   │       ├── fDrvBwazEqwezTJaFVuRfo5lCWU=
│   │   │   │   │       ├── fqbjhNolEHyqugYTT+lDbRF+rPQ=
│   │   │   │   │       ├── hA0+PoduGqNYxbr5w5Pjr+5dguA=
│   │   │   │   │       ├── hazQ60DO5s0T4XEiwqKaoS8U75w=
│   │   │   │   │       ├── iHX_4py8xdOpQSNjuhp+i4RpNJA=
│   │   │   │   │       ├── jIEFQVBi1zmy33kCwCz1ga6lDQg=
│   │   │   │   │       ├── kFQZwetldMkXHV2s7M8YFIJkhg4=
│   │   │   │   │       ├── mYQX3vFq5Iqf1SpIEo36EXg70GU=
│   │   │   │   │       ├── mxfAjJW131MyIfQmAmATmuEFa0I=
│   │   │   │   │       ├── nhWD8PlwE0TyacITvlrcG0ltPWU=
│   │   │   │   │       ├── ogS9tTlBeLCtOqFQhy8uwRK6pwM=
│   │   │   │   │       ├── poKr9SdG8KmzBvSL10Umdl8GQjc=
│   │   │   │   │       ├── rzbqj0eiUlMBqFdJfGcJY6K7EZw=
│   │   │   │   │       ├── s4GHHSePhCoQsxWLGGL+ydVJg3I=
│   │   │   │   │       ├── wZVPWZ7C6yjk1512_qlyosUDadY=
│   │   │   │   │       ├── ycIdvI6wJXHDs9dLkn_MM_ba4Ks=
│   │   │   │   │       └── yxyzj0J8Vy3xePnPmegMedH1wqU=
│   │   │   │   ├── mergeDebugAssets
│   │   │   │   │   └── merger.xml
│   │   │   │   ├── mergeDebugJniLibFolders
│   │   │   │   │   └── merger.xml
│   │   │   │   ├── mergeDebugResources
│   │   │   │   │   ├── compile-file-map.properties
│   │   │   │   │   ├── merged.dir
│   │   │   │   │   │   ├── values
│   │   │   │   │   │   │   └── values.xml
│   │   │   │   │   │   ├── values-af
│   │   │   │   │   │   │   └── values-af.xml
│   │   │   │   │   │   ├── values-am
│   │   │   │   │   │   │   └── values-am.xml
│   │   │   │   │   │   ├── values-ar
│   │   │   │   │   │   │   └── values-ar.xml
│   │   │   │   │   │   ├── values-as
│   │   │   │   │   │   │   └── values-as.xml
│   │   │   │   │   │   ├── values-az
│   │   │   │   │   │   │   └── values-az.xml
│   │   │   │   │   │   ├── values-b+sr+Latn
│   │   │   │   │   │   │   └── values-b+sr+Latn.xml
│   │   │   │   │   │   ├── values-be
│   │   │   │   │   │   │   └── values-be.xml
│   │   │   │   │   │   ├── values-bg
│   │   │   │   │   │   │   └── values-bg.xml
│   │   │   │   │   │   ├── values-bn
│   │   │   │   │   │   │   └── values-bn.xml
│   │   │   │   │   │   ├── values-bs
│   │   │   │   │   │   │   └── values-bs.xml
│   │   │   │   │   │   ├── values-ca
│   │   │   │   │   │   │   └── values-ca.xml
│   │   │   │   │   │   ├── values-cs
│   │   │   │   │   │   │   └── values-cs.xml
│   │   │   │   │   │   ├── values-da
│   │   │   │   │   │   │   └── values-da.xml
│   │   │   │   │   │   ├── values-de
│   │   │   │   │   │   │   └── values-de.xml
│   │   │   │   │   │   ├── values-el
│   │   │   │   │   │   │   └── values-el.xml
│   │   │   │   │   │   ├── values-en-rAU
│   │   │   │   │   │   │   └── values-en-rAU.xml
│   │   │   │   │   │   ├── values-en-rCA
│   │   │   │   │   │   │   └── values-en-rCA.xml
│   │   │   │   │   │   ├── values-en-rGB
│   │   │   │   │   │   │   └── values-en-rGB.xml
│   │   │   │   │   │   ├── values-en-rIN
│   │   │   │   │   │   │   └── values-en-rIN.xml
│   │   │   │   │   │   ├── values-en-rXC
│   │   │   │   │   │   │   └── values-en-rXC.xml
│   │   │   │   │   │   ├── values-es
│   │   │   │   │   │   │   └── values-es.xml
│   │   │   │   │   │   ├── values-es-rUS
│   │   │   │   │   │   │   └── values-es-rUS.xml
│   │   │   │   │   │   ├── values-et
│   │   │   │   │   │   │   └── values-et.xml
│   │   │   │   │   │   ├── values-eu
│   │   │   │   │   │   │   └── values-eu.xml
│   │   │   │   │   │   ├── values-fa
│   │   │   │   │   │   │   └── values-fa.xml
│   │   │   │   │   │   ├── values-fi
│   │   │   │   │   │   │   └── values-fi.xml
│   │   │   │   │   │   ├── values-fr
│   │   │   │   │   │   │   └── values-fr.xml
│   │   │   │   │   │   ├── values-fr-rCA
│   │   │   │   │   │   │   └── values-fr-rCA.xml
│   │   │   │   │   │   ├── values-gl
│   │   │   │   │   │   │   └── values-gl.xml
│   │   │   │   │   │   ├── values-gu
│   │   │   │   │   │   │   └── values-gu.xml
│   │   │   │   │   │   ├── values-h720dp-v13
│   │   │   │   │   │   │   └── values-h720dp-v13.xml
│   │   │   │   │   │   ├── values-hdpi-v4
│   │   │   │   │   │   │   └── values-hdpi-v4.xml
│   │   │   │   │   │   ├── values-hi
│   │   │   │   │   │   │   └── values-hi.xml
│   │   │   │   │   │   ├── values-hr
│   │   │   │   │   │   │   └── values-hr.xml
│   │   │   │   │   │   ├── values-hu
│   │   │   │   │   │   │   └── values-hu.xml
│   │   │   │   │   │   ├── values-hy
│   │   │   │   │   │   │   └── values-hy.xml
│   │   │   │   │   │   ├── values-in
│   │   │   │   │   │   │   └── values-in.xml
│   │   │   │   │   │   ├── values-is
│   │   │   │   │   │   │   └── values-is.xml
│   │   │   │   │   │   ├── values-it
│   │   │   │   │   │   │   └── values-it.xml
│   │   │   │   │   │   ├── values-iw
│   │   │   │   │   │   │   └── values-iw.xml
│   │   │   │   │   │   ├── values-ja
│   │   │   │   │   │   │   └── values-ja.xml
│   │   │   │   │   │   ├── values-ka
│   │   │   │   │   │   │   └── values-ka.xml
│   │   │   │   │   │   ├── values-kk
│   │   │   │   │   │   │   └── values-kk.xml
│   │   │   │   │   │   ├── values-km
│   │   │   │   │   │   │   └── values-km.xml
│   │   │   │   │   │   ├── values-kn
│   │   │   │   │   │   │   └── values-kn.xml
│   │   │   │   │   │   ├── values-ko
│   │   │   │   │   │   │   └── values-ko.xml
│   │   │   │   │   │   ├── values-ky
│   │   │   │   │   │   │   └── values-ky.xml
│   │   │   │   │   │   ├── values-land
│   │   │   │   │   │   │   └── values-land.xml
│   │   │   │   │   │   ├── values-large-v4
│   │   │   │   │   │   │   └── values-large-v4.xml
│   │   │   │   │   │   ├── values-ldltr-v21
│   │   │   │   │   │   │   └── values-ldltr-v21.xml
│   │   │   │   │   │   ├── values-lo
│   │   │   │   │   │   │   └── values-lo.xml
│   │   │   │   │   │   ├── values-lt
│   │   │   │   │   │   │   └── values-lt.xml
│   │   │   │   │   │   ├── values-lv
│   │   │   │   │   │   │   └── values-lv.xml
│   │   │   │   │   │   ├── values-mk
│   │   │   │   │   │   │   └── values-mk.xml
│   │   │   │   │   │   ├── values-ml
│   │   │   │   │   │   │   └── values-ml.xml
│   │   │   │   │   │   ├── values-mn
│   │   │   │   │   │   │   └── values-mn.xml
│   │   │   │   │   │   ├── values-mr
│   │   │   │   │   │   │   └── values-mr.xml
│   │   │   │   │   │   ├── values-ms
│   │   │   │   │   │   │   └── values-ms.xml
│   │   │   │   │   │   ├── values-my
│   │   │   │   │   │   │   └── values-my.xml
│   │   │   │   │   │   ├── values-nb
│   │   │   │   │   │   │   └── values-nb.xml
│   │   │   │   │   │   ├── values-ne
│   │   │   │   │   │   │   └── values-ne.xml
│   │   │   │   │   │   ├── values-night-v8
│   │   │   │   │   │   │   └── values-night-v8.xml
│   │   │   │   │   │   ├── values-nl
│   │   │   │   │   │   │   └── values-nl.xml
│   │   │   │   │   │   ├── values-or
│   │   │   │   │   │   │   └── values-or.xml
│   │   │   │   │   │   ├── values-pa
│   │   │   │   │   │   │   └── values-pa.xml
│   │   │   │   │   │   ├── values-pl
│   │   │   │   │   │   │   └── values-pl.xml
│   │   │   │   │   │   ├── values-port
│   │   │   │   │   │   │   └── values-port.xml
│   │   │   │   │   │   ├── values-pt
│   │   │   │   │   │   │   └── values-pt.xml
│   │   │   │   │   │   ├── values-pt-rBR
│   │   │   │   │   │   │   └── values-pt-rBR.xml
│   │   │   │   │   │   ├── values-pt-rPT
│   │   │   │   │   │   │   └── values-pt-rPT.xml
│   │   │   │   │   │   ├── values-ro
│   │   │   │   │   │   │   └── values-ro.xml
│   │   │   │   │   │   ├── values-ru
│   │   │   │   │   │   │   └── values-ru.xml
│   │   │   │   │   │   ├── values-si
│   │   │   │   │   │   │   └── values-si.xml
│   │   │   │   │   │   ├── values-sk
│   │   │   │   │   │   │   └── values-sk.xml
│   │   │   │   │   │   ├── values-sl
│   │   │   │   │   │   │   └── values-sl.xml
│   │   │   │   │   │   ├── values-sq
│   │   │   │   │   │   │   └── values-sq.xml
│   │   │   │   │   │   ├── values-sr
│   │   │   │   │   │   │   └── values-sr.xml
│   │   │   │   │   │   ├── values-sv
│   │   │   │   │   │   │   └── values-sv.xml
│   │   │   │   │   │   ├── values-sw
│   │   │   │   │   │   │   └── values-sw.xml
│   │   │   │   │   │   ├── values-sw600dp-v13
│   │   │   │   │   │   │   └── values-sw600dp-v13.xml
│   │   │   │   │   │   ├── values-ta
│   │   │   │   │   │   │   └── values-ta.xml
│   │   │   │   │   │   ├── values-te
│   │   │   │   │   │   │   └── values-te.xml
│   │   │   │   │   │   ├── values-th
│   │   │   │   │   │   │   └── values-th.xml
│   │   │   │   │   │   ├── values-tl
│   │   │   │   │   │   │   └── values-tl.xml
│   │   │   │   │   │   ├── values-tr
│   │   │   │   │   │   │   └── values-tr.xml
│   │   │   │   │   │   ├── values-uk
│   │   │   │   │   │   │   └── values-uk.xml
│   │   │   │   │   │   ├── values-ur
│   │   │   │   │   │   │   └── values-ur.xml
│   │   │   │   │   │   ├── values-uz
│   │   │   │   │   │   │   └── values-uz.xml
│   │   │   │   │   │   ├── values-v16
│   │   │   │   │   │   │   └── values-v16.xml
│   │   │   │   │   │   ├── values-v17
│   │   │   │   │   │   │   └── values-v17.xml
│   │   │   │   │   │   ├── values-v18
│   │   │   │   │   │   │   └── values-v18.xml
│   │   │   │   │   │   ├── values-v21
│   │   │   │   │   │   │   └── values-v21.xml
│   │   │   │   │   │   ├── values-v22
│   │   │   │   │   │   │   └── values-v22.xml
│   │   │   │   │   │   ├── values-v23
│   │   │   │   │   │   │   └── values-v23.xml
│   │   │   │   │   │   ├── values-v24
│   │   │   │   │   │   │   └── values-v24.xml
│   │   │   │   │   │   ├── values-v25
│   │   │   │   │   │   │   └── values-v25.xml
│   │   │   │   │   │   ├── values-v26
│   │   │   │   │   │   │   └── values-v26.xml
│   │   │   │   │   │   ├── values-v28
│   │   │   │   │   │   │   └── values-v28.xml
│   │   │   │   │   │   ├── values-vi
│   │   │   │   │   │   │   └── values-vi.xml
│   │   │   │   │   │   ├── values-watch-v20
│   │   │   │   │   │   │   └── values-watch-v20.xml
│   │   │   │   │   │   ├── values-watch-v21
│   │   │   │   │   │   │   └── values-watch-v21.xml
│   │   │   │   │   │   ├── values-xlarge-v4
│   │   │   │   │   │   │   └── values-xlarge-v4.xml
│   │   │   │   │   │   ├── values-zh-rCN
│   │   │   │   │   │   │   └── values-zh-rCN.xml
│   │   │   │   │   │   ├── values-zh-rHK
│   │   │   │   │   │   │   └── values-zh-rHK.xml
│   │   │   │   │   │   ├── values-zh-rTW
│   │   │   │   │   │   │   └── values-zh-rTW.xml
│   │   │   │   │   │   └── values-zu
│   │   │   │   │   │       └── values-zu.xml
│   │   │   │   │   ├── merger.xml
│   │   │   │   │   └── stripped.dir
│   │   │   │   ├── mergeDebugShaders
│   │   │   │   │   └── merger.xml
│   │   │   │   ├── packageDebug
│   │   │   │   │   └── tmp
│   │   │   │   │       └── debug
│   │   │   │   │           ├── dex-renamer-state.txt
│   │   │   │   │           └── zip-cache
│   │   │   │   │               ├── BiBIHVlvF9vfA3pdwowS5tNBb3M=
│   │   │   │   │               └── U5J0JnW7vKZX5PNhLGa69H1S+Bs=
│   │   │   │   └── processDebugResources
│   │   │   │       └── resources-list-for-resources-debug.ap_.txt
│   │   │   ├── instant_app_manifest
│   │   │   │   └── debug
│   │   │   │       ├── AndroidManifest.xml
│   │   │   │       └── output.json
│   │   │   ├── javac
│   │   │   │   └── debug
│   │   │   │       └── classes
│   │   │   │           ├── androidx
│   │   │   │           │   ├── activity
│   │   │   │           │   │   ├── R$attr.class
│   │   │   │           │   │   ├── R$color.class
│   │   │   │           │   │   ├── R$dimen.class
│   │   │   │           │   │   ├── R$drawable.class
│   │   │   │           │   │   ├── R$id.class
│   │   │   │           │   │   ├── R$integer.class
│   │   │   │           │   │   ├── R$layout.class
│   │   │   │           │   │   ├── R$string.class
│   │   │   │           │   │   ├── R$style.class
│   │   │   │           │   │   ├── R$styleable.class
│   │   │   │           │   │   └── R.class
│   │   │   │           │   ├── appcompat
│   │   │   │           │   │   ├── R$anim.class
│   │   │   │           │   │   ├── R$attr.class
│   │   │   │           │   │   ├── R$bool.class
│   │   │   │           │   │   ├── R$color.class
│   │   │   │           │   │   ├── R$dimen.class
│   │   │   │           │   │   ├── R$drawable.class
│   │   │   │           │   │   ├── R$id.class
│   │   │   │           │   │   ├── R$integer.class
│   │   │   │           │   │   ├── R$interpolator.class
│   │   │   │           │   │   ├── R$layout.class
│   │   │   │           │   │   ├── R$string.class
│   │   │   │           │   │   ├── R$style.class
│   │   │   │           │   │   ├── R$styleable.class
│   │   │   │           │   │   ├── R.class
│   │   │   │           │   │   └── resources
│   │   │   │           │   │       ├── R$attr.class
│   │   │   │           │   │       ├── R$color.class
│   │   │   │           │   │       ├── R$dimen.class
│   │   │   │           │   │       ├── R$drawable.class
│   │   │   │           │   │       ├── R$id.class
│   │   │   │           │   │       ├── R$integer.class
│   │   │   │           │   │       ├── R$layout.class
│   │   │   │           │   │       ├── R$string.class
│   │   │   │           │   │       ├── R$style.class
│   │   │   │           │   │       ├── R$styleable.class
│   │   │   │           │   │       └── R.class
│   │   │   │           │   ├── arch
│   │   │   │           │   │   └── core
│   │   │   │           │   │       └── R.class
│   │   │   │           │   ├── constraintlayout
│   │   │   │           │   │   └── widget
│   │   │   │           │   │       ├── R$attr.class
│   │   │   │           │   │       ├── R$id.class
│   │   │   │           │   │       ├── R$styleable.class
│   │   │   │           │   │       └── R.class
│   │   │   │           │   ├── core
│   │   │   │           │   │   ├── R$attr.class
│   │   │   │           │   │   ├── R$color.class
│   │   │   │           │   │   ├── R$dimen.class
│   │   │   │           │   │   ├── R$drawable.class
│   │   │   │           │   │   ├── R$id.class
│   │   │   │           │   │   ├── R$integer.class
│   │   │   │           │   │   ├── R$layout.class
│   │   │   │           │   │   ├── R$string.class
│   │   │   │           │   │   ├── R$style.class
│   │   │   │           │   │   ├── R$styleable.class
│   │   │   │           │   │   └── R.class
│   │   │   │           │   ├── cursoradapter
│   │   │   │           │   │   └── R.class
│   │   │   │           │   ├── customview
│   │   │   │           │   │   ├── R$attr.class
│   │   │   │           │   │   ├── R$color.class
│   │   │   │           │   │   ├── R$dimen.class
│   │   │   │           │   │   ├── R$drawable.class
│   │   │   │           │   │   ├── R$id.class
│   │   │   │           │   │   ├── R$integer.class
│   │   │   │           │   │   ├── R$layout.class
│   │   │   │           │   │   ├── R$string.class
│   │   │   │           │   │   ├── R$style.class
│   │   │   │           │   │   ├── R$styleable.class
│   │   │   │           │   │   └── R.class
│   │   │   │           │   ├── documentfile
│   │   │   │           │   │   └── R.class
│   │   │   │           │   ├── drawerlayout
│   │   │   │           │   │   ├── R$attr.class
│   │   │   │           │   │   ├── R$color.class
│   │   │   │           │   │   ├── R$dimen.class
│   │   │   │           │   │   ├── R$drawable.class
│   │   │   │           │   │   ├── R$id.class
│   │   │   │           │   │   ├── R$integer.class
│   │   │   │           │   │   ├── R$layout.class
│   │   │   │           │   │   ├── R$string.class
│   │   │   │           │   │   ├── R$style.class
│   │   │   │           │   │   ├── R$styleable.class
│   │   │   │           │   │   └── R.class
│   │   │   │           │   ├── fragment
│   │   │   │           │   │   ├── R$attr.class
│   │   │   │           │   │   ├── R$color.class
│   │   │   │           │   │   ├── R$dimen.class
│   │   │   │           │   │   ├── R$drawable.class
│   │   │   │           │   │   ├── R$id.class
│   │   │   │           │   │   ├── R$integer.class
│   │   │   │           │   │   ├── R$layout.class
│   │   │   │           │   │   ├── R$string.class
│   │   │   │           │   │   ├── R$style.class
│   │   │   │           │   │   ├── R$styleable.class
│   │   │   │           │   │   └── R.class
│   │   │   │           │   ├── interpolator
│   │   │   │           │   │   └── R.class
│   │   │   │           │   ├── legacy
│   │   │   │           │   │   └── coreutils
│   │   │   │           │   │       ├── R$attr.class
│   │   │   │           │   │       ├── R$color.class
│   │   │   │           │   │       ├── R$dimen.class
│   │   │   │           │   │       ├── R$drawable.class
│   │   │   │           │   │       ├── R$id.class
│   │   │   │           │   │       ├── R$integer.class
│   │   │   │           │   │       ├── R$layout.class
│   │   │   │           │   │       ├── R$string.class
│   │   │   │           │   │       ├── R$style.class
│   │   │   │           │   │       ├── R$styleable.class
│   │   │   │           │   │       └── R.class
│   │   │   │           │   ├── lifecycle
│   │   │   │           │   │   ├── R.class
│   │   │   │           │   │   ├── livedata
│   │   │   │           │   │   │   ├── R.class
│   │   │   │           │   │   │   └── core
│   │   │   │           │   │   │       └── R.class
│   │   │   │           │   │   └── viewmodel
│   │   │   │           │   │       └── R.class
│   │   │   │           │   ├── loader
│   │   │   │           │   │   ├── R$attr.class
│   │   │   │           │   │   ├── R$color.class
│   │   │   │           │   │   ├── R$dimen.class
│   │   │   │           │   │   ├── R$drawable.class
│   │   │   │           │   │   ├── R$id.class
│   │   │   │           │   │   ├── R$integer.class
│   │   │   │           │   │   ├── R$layout.class
│   │   │   │           │   │   ├── R$string.class
│   │   │   │           │   │   ├── R$style.class
│   │   │   │           │   │   ├── R$styleable.class
│   │   │   │           │   │   └── R.class
│   │   │   │           │   ├── localbroadcastmanager
│   │   │   │           │   │   └── R.class
│   │   │   │           │   ├── print
│   │   │   │           │   │   └── R.class
│   │   │   │           │   ├── savedstate
│   │   │   │           │   │   └── R.class
│   │   │   │           │   ├── vectordrawable
│   │   │   │           │   │   ├── R$attr.class
│   │   │   │           │   │   ├── R$color.class
│   │   │   │           │   │   ├── R$dimen.class
│   │   │   │           │   │   ├── R$drawable.class
│   │   │   │           │   │   ├── R$id.class
│   │   │   │           │   │   ├── R$integer.class
│   │   │   │           │   │   ├── R$layout.class
│   │   │   │           │   │   ├── R$string.class
│   │   │   │           │   │   ├── R$style.class
│   │   │   │           │   │   ├── R$styleable.class
│   │   │   │           │   │   ├── R.class
│   │   │   │           │   │   └── animated
│   │   │   │           │   │       ├── R$attr.class
│   │   │   │           │   │       ├── R$color.class
│   │   │   │           │   │       ├── R$dimen.class
│   │   │   │           │   │       ├── R$drawable.class
│   │   │   │           │   │       ├── R$id.class
│   │   │   │           │   │       ├── R$integer.class
│   │   │   │           │   │       ├── R$layout.class
│   │   │   │           │   │       ├── R$string.class
│   │   │   │           │   │       ├── R$style.class
│   │   │   │           │   │       ├── R$styleable.class
│   │   │   │           │   │       └── R.class
│   │   │   │           │   ├── versionedparcelable
│   │   │   │           │   │   └── R.class
│   │   │   │           │   └── viewpager
│   │   │   │           │       ├── R$attr.class
│   │   │   │           │       ├── R$color.class
│   │   │   │           │       ├── R$dimen.class
│   │   │   │           │       ├── R$drawable.class
│   │   │   │           │       ├── R$id.class
│   │   │   │           │       ├── R$integer.class
│   │   │   │           │       ├── R$layout.class
│   │   │   │           │       ├── R$string.class
│   │   │   │           │       ├── R$style.class
│   │   │   │           │       ├── R$styleable.class
│   │   │   │           │       └── R.class
│   │   │   │           └── com
│   │   │   │               ├── example
│   │   │   │               │   └── coronaMapProject
│   │   │   │               │       ├── BuildConfig.class
│   │   │   │               │       ├── CoronaLocation.class
│   │   │   │               │       ├── CoronaLocationNearAlertService$1.class
│   │   │   │               │       ├── CoronaLocationNearAlertService$MyBinder.class
│   │   │   │               │       ├── CoronaLocationNearAlertService$MyLocationListener.class
│   │   │   │               │       ├── CoronaLocationNearAlertService.class
│   │   │   │               │       ├── CoronaMapActivity$1.class
│   │   │   │               │       ├── CoronaMapActivity$MyLocation.class
│   │   │   │               │       ├── CoronaMapActivity.class
│   │   │   │               │       ├── CoronaMapAllActivity$1.class
│   │   │   │               │       ├── CoronaMapAllActivity$MyLocation.class
│   │   │   │               │       ├── CoronaMapAllActivity.class
│   │   │   │               │       ├── CoronoLocationActivity$LocationAdapter.class
│   │   │   │               │       ├── CoronoLocationActivity.class
│   │   │   │               │       ├── GpsTracker.class
│   │   │   │               │       ├── HttpHandler.class
│   │   │   │               │       ├── Item.class
│   │   │   │               │       ├── MainActivity$HttpTask.class
│   │   │   │               │       ├── MainActivity.class
│   │   │   │               │       ├── MyFirebaseMessagingService$1.class
│   │   │   │               │       ├── MyFirebaseMessagingService.class
│   │   │   │               │       ├── R$anim.class
│   │   │   │               │       ├── R$attr.class
│   │   │   │               │       ├── R$bool.class
│   │   │   │               │       ├── R$color.class
│   │   │   │               │       ├── R$dimen.class
│   │   │   │               │       ├── R$drawable.class
│   │   │   │               │       ├── R$id.class
│   │   │   │               │       ├── R$integer.class
│   │   │   │               │       ├── R$interpolator.class
│   │   │   │               │       ├── R$layout.class
│   │   │   │               │       ├── R$mipmap.class
│   │   │   │               │       ├── R$raw.class
│   │   │   │               │       ├── R$string.class
│   │   │   │               │       ├── R$style.class
│   │   │   │               │       ├── R$styleable.class
│   │   │   │               │       ├── R.class
│   │   │   │               │       ├── SecondActivity$ItemAdapter$1$1.class
│   │   │   │               │       ├── SecondActivity$ItemAdapter$1.class
│   │   │   │               │       ├── SecondActivity$ItemAdapter.class
│   │   │   │               │       ├── SecondActivity$ItemAsync$1.class
│   │   │   │               │       ├── SecondActivity$ItemAsync.class
│   │   │   │               │       ├── SecondActivity.class
│   │   │   │               │       └── Temp.class
│   │   │   │               └── google
│   │   │   │                   ├── android
│   │   │   │                   │   └── gms
│   │   │   │                   │       ├── ads_identifier
│   │   │   │                   │       │   └── R.class
│   │   │   │                   │       ├── base
│   │   │   │                   │       │   ├── R$attr.class
│   │   │   │                   │       │   ├── R$color.class
│   │   │   │                   │       │   ├── R$drawable.class
│   │   │   │                   │       │   ├── R$id.class
│   │   │   │                   │       │   ├── R$string.class
│   │   │   │                   │       │   ├── R$styleable.class
│   │   │   │                   │       │   └── R.class
│   │   │   │                   │       ├── common
│   │   │   │                   │       │   ├── R$integer.class
│   │   │   │                   │       │   ├── R$string.class
│   │   │   │                   │       │   └── R.class
│   │   │   │                   │       ├── maps
│   │   │   │                   │       │   ├── R$attr.class
│   │   │   │                   │       │   ├── R$id.class
│   │   │   │                   │       │   ├── R$styleable.class
│   │   │   │                   │       │   └── R.class
│   │   │   │                   │       ├── measurement
│   │   │   │                   │       │   ├── api
│   │   │   │                   │       │   │   └── R.class
│   │   │   │                   │       │   └── sdk
│   │   │   │                   │       │       ├── R.class
│   │   │   │                   │       │       └── api
│   │   │   │                   │       │           └── R.class
│   │   │   │                   │       ├── measurement_base
│   │   │   │                   │       │   └── R.class
│   │   │   │                   │       ├── stats
│   │   │   │                   │       │   └── R.class
│   │   │   │                   │       └── tasks
│   │   │   │                   │           └── R.class
│   │   │   │                   └── firebase
│   │   │   │                       ├── R$attr.class
│   │   │   │                       ├── R$color.class
│   │   │   │                       ├── R$dimen.class
│   │   │   │                       ├── R$drawable.class
│   │   │   │                       ├── R$id.class
│   │   │   │                       ├── R$integer.class
│   │   │   │                       ├── R$layout.class
│   │   │   │                       ├── R$string.class
│   │   │   │                       ├── R$style.class
│   │   │   │                       ├── R$styleable.class
│   │   │   │                       ├── R.class
│   │   │   │                       ├── analytics
│   │   │   │                       │   └── connector
│   │   │   │                       │       └── R.class
│   │   │   │                       ├── firebase_analytics
│   │   │   │                       │   └── R.class
│   │   │   │                       ├── firebase_core
│   │   │   │                       │   └── R.class
│   │   │   │                       ├── iid
│   │   │   │                       │   ├── R.class
│   │   │   │                       │   └── internal
│   │   │   │                       │       └── R.class
│   │   │   │                       ├── measurement
│   │   │   │                       │   └── R.class
│   │   │   │                       ├── measurement_impl
│   │   │   │                       │   └── R.class
│   │   │   │                       └── messaging
│   │   │   │                           ├── R$string.class
│   │   │   │                           └── R.class
│   │   │   ├── lint_jar
│   │   │   │   └── global
│   │   │   │       └── prepareLintJar
│   │   │   ├── lint_publish_jar
│   │   │   │   └── global
│   │   │   │       └── prepareLintJarForPublish
│   │   │   ├── manifest_merge_blame_file
│   │   │   │   ├── debug
│   │   │   │   │   └── manifest-merger-blame-debug-report.txt
│   │   │   │   └── debugAndroidTest
│   │   │   │       └── manifest-merger-blame-debug-androidTest-report.txt
│   │   │   ├── merged_assets
│   │   │   │   └── debug
│   │   │   │       └── out
│   │   │   ├── merged_java_res
│   │   │   │   └── debug
│   │   │   │       └── out.jar
│   │   │   ├── merged_jni_libs
│   │   │   │   └── debug
│   │   │   │       └── out
│   │   │   ├── merged_manifests
│   │   │   │   ├── debug
│   │   │   │   │   ├── AndroidManifest.xml
│   │   │   │   │   └── output.json
│   │   │   │   └── debugAndroidTest
│   │   │   │       ├── AndroidManifest.xml
│   │   │   │       └── output.json
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
│   │   │   │               └── output.json
│   │   │   ├── processed_res
│   │   │   │   └── debug
│   │   │   │       └── processDebugResources
│   │   │   │           └── out
│   │   │   │               ├── output.json
│   │   │   │               └── resources-debug.ap_
│   │   │   ├── res
│   │   │   │   ├── merged
│   │   │   │   │   └── debug
│   │   │   │   │       ├── anim_abc_fade_in.xml.flat
│   │   │   │   │       ├── anim_abc_fade_out.xml.flat
│   │   │   │   │       ├── anim_abc_grow_fade_in_from_bottom.xml.flat
│   │   │   │   │       ├── anim_abc_popup_enter.xml.flat
│   │   │   │   │       ├── anim_abc_popup_exit.xml.flat
│   │   │   │   │       ├── anim_abc_shrink_fade_out_from_bottom.xml.flat
│   │   │   │   │       ├── anim_abc_slide_in_bottom.xml.flat
│   │   │   │   │       ├── anim_abc_slide_in_top.xml.flat
│   │   │   │   │       ├── anim_abc_slide_out_bottom.xml.flat
│   │   │   │   │       ├── anim_abc_slide_out_top.xml.flat
│   │   │   │   │       ├── anim_abc_tooltip_enter.xml.flat
│   │   │   │   │       ├── anim_abc_tooltip_exit.xml.flat
│   │   │   │   │       ├── anim_btn_checkbox_to_checked_box_inner_merged_animation.xml.flat
│   │   │   │   │       ├── anim_btn_checkbox_to_checked_box_outer_merged_animation.xml.flat
│   │   │   │   │       ├── anim_btn_checkbox_to_checked_icon_null_animation.xml.flat
│   │   │   │   │       ├── anim_btn_checkbox_to_unchecked_box_inner_merged_animation.xml.flat
│   │   │   │   │       ├── anim_btn_checkbox_to_unchecked_check_path_merged_animation.xml.flat
│   │   │   │   │       ├── anim_btn_checkbox_to_unchecked_icon_null_animation.xml.flat
│   │   │   │   │       ├── anim_btn_radio_to_off_mtrl_dot_group_animation.xml.flat
│   │   │   │   │       ├── anim_btn_radio_to_off_mtrl_ring_outer_animation.xml.flat
│   │   │   │   │       ├── anim_btn_radio_to_off_mtrl_ring_outer_path_animation.xml.flat
│   │   │   │   │       ├── anim_btn_radio_to_on_mtrl_dot_group_animation.xml.flat
│   │   │   │   │       ├── anim_btn_radio_to_on_mtrl_ring_outer_animation.xml.flat
│   │   │   │   │       ├── anim_btn_radio_to_on_mtrl_ring_outer_path_animation.xml.flat
│   │   │   │   │       ├── color-v23_abc_btn_colored_borderless_text_material.xml.flat
│   │   │   │   │       ├── color-v23_abc_btn_colored_text_material.xml.flat
│   │   │   │   │       ├── color-v23_abc_color_highlight_material.xml.flat
│   │   │   │   │       ├── color-v23_abc_tint_btn_checkable.xml.flat
│   │   │   │   │       ├── color-v23_abc_tint_default.xml.flat
│   │   │   │   │       ├── color-v23_abc_tint_edittext.xml.flat
│   │   │   │   │       ├── color-v23_abc_tint_seek_thumb.xml.flat
│   │   │   │   │       ├── color-v23_abc_tint_spinner.xml.flat
│   │   │   │   │       ├── color-v23_abc_tint_switch_track.xml.flat
│   │   │   │   │       ├── color_abc_background_cache_hint_selector_material_dark.xml.flat
│   │   │   │   │       ├── color_abc_background_cache_hint_selector_material_light.xml.flat
│   │   │   │   │       ├── color_abc_hint_foreground_material_dark.xml.flat
│   │   │   │   │       ├── color_abc_hint_foreground_material_light.xml.flat
│   │   │   │   │       ├── color_abc_primary_text_disable_only_material_dark.xml.flat
│   │   │   │   │       ├── color_abc_primary_text_disable_only_material_light.xml.flat
│   │   │   │   │       ├── color_abc_primary_text_material_dark.xml.flat
│   │   │   │   │       ├── color_abc_primary_text_material_light.xml.flat
│   │   │   │   │       ├── color_abc_search_url_text.xml.flat
│   │   │   │   │       ├── color_abc_secondary_text_material_dark.xml.flat
│   │   │   │   │       ├── color_abc_secondary_text_material_light.xml.flat
│   │   │   │   │       ├── color_common_google_signin_btn_text_dark.xml.flat
│   │   │   │   │       ├── color_common_google_signin_btn_text_light.xml.flat
│   │   │   │   │       ├── color_common_google_signin_btn_tint.xml.flat
│   │   │   │   │       ├── color_switch_thumb_material_dark.xml.flat
│   │   │   │   │       ├── color_switch_thumb_material_light.xml.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_ab_share_pack_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_btn_check_to_on_mtrl_000.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_btn_check_to_on_mtrl_015.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_btn_radio_to_on_mtrl_000.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_btn_radio_to_on_mtrl_015.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_btn_switch_to_on_mtrl_00001.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_btn_switch_to_on_mtrl_00012.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_cab_background_top_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_ic_commit_search_api_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_ic_menu_copy_mtrl_am_alpha.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_ic_menu_cut_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_ic_menu_paste_mtrl_am_alpha.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_ic_menu_selectall_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_ic_menu_share_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_ic_star_black_16dp.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_ic_star_black_36dp.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_ic_star_black_48dp.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_ic_star_half_black_16dp.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_ic_star_half_black_36dp.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_ic_star_half_black_48dp.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_list_divider_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_list_focused_holo.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_list_longpressed_holo.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_list_pressed_holo_dark.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_list_pressed_holo_light.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_list_selector_disabled_holo_dark.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_list_selector_disabled_holo_light.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_menu_hardkey_panel_mtrl_mult.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_popup_background_mtrl_mult.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_scrubber_control_off_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_scrubber_control_to_pressed_mtrl_000.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_scrubber_control_to_pressed_mtrl_005.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_scrubber_primary_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_scrubber_track_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_spinner_mtrl_am_alpha.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_switch_track_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_tab_indicator_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_text_select_handle_left_mtrl_dark.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_text_select_handle_left_mtrl_light.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_text_select_handle_middle_mtrl_dark.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_text_select_handle_middle_mtrl_light.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_text_select_handle_right_mtrl_dark.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_text_select_handle_right_mtrl_light.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_textfield_activated_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_textfield_default_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_textfield_search_activated_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_abc_textfield_search_default_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_common_full_open_on_phone.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_common_google_signin_btn_icon_dark_normal_background.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_common_google_signin_btn_icon_light_normal_background.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_common_google_signin_btn_text_dark_normal_background.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_common_google_signin_btn_text_light_normal_background.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_googleg_disabled_color_18.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_googleg_standard_color_18.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_notification_bg_low_normal.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_notification_bg_low_pressed.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_notification_bg_normal.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_notification_bg_normal_pressed.9.png.flat
│   │   │   │   │       ├── drawable-hdpi-v4_notify_panel_notification_icon_bg.png.flat
│   │   │   │   │       ├── drawable-ldrtl-hdpi-v17_abc_ic_menu_copy_mtrl_am_alpha.png.flat
│   │   │   │   │       ├── drawable-ldrtl-hdpi-v17_abc_ic_menu_cut_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-ldrtl-hdpi-v17_abc_spinner_mtrl_am_alpha.9.png.flat
│   │   │   │   │       ├── drawable-ldrtl-mdpi-v17_abc_ic_menu_copy_mtrl_am_alpha.png.flat
│   │   │   │   │       ├── drawable-ldrtl-mdpi-v17_abc_ic_menu_cut_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-ldrtl-mdpi-v17_abc_spinner_mtrl_am_alpha.9.png.flat
│   │   │   │   │       ├── drawable-ldrtl-xhdpi-v17_abc_ic_menu_copy_mtrl_am_alpha.png.flat
│   │   │   │   │       ├── drawable-ldrtl-xhdpi-v17_abc_ic_menu_cut_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-ldrtl-xhdpi-v17_abc_spinner_mtrl_am_alpha.9.png.flat
│   │   │   │   │       ├── drawable-ldrtl-xxhdpi-v17_abc_ic_menu_copy_mtrl_am_alpha.png.flat
│   │   │   │   │       ├── drawable-ldrtl-xxhdpi-v17_abc_ic_menu_cut_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-ldrtl-xxhdpi-v17_abc_spinner_mtrl_am_alpha.9.png.flat
│   │   │   │   │       ├── drawable-ldrtl-xxxhdpi-v17_abc_ic_menu_copy_mtrl_am_alpha.png.flat
│   │   │   │   │       ├── drawable-ldrtl-xxxhdpi-v17_abc_ic_menu_cut_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-ldrtl-xxxhdpi-v17_abc_spinner_mtrl_am_alpha.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_ab_share_pack_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_btn_check_to_on_mtrl_000.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_btn_check_to_on_mtrl_015.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_btn_radio_to_on_mtrl_000.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_btn_radio_to_on_mtrl_015.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_btn_switch_to_on_mtrl_00001.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_btn_switch_to_on_mtrl_00012.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_cab_background_top_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_ic_commit_search_api_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_ic_menu_copy_mtrl_am_alpha.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_ic_menu_cut_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_ic_menu_paste_mtrl_am_alpha.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_ic_menu_selectall_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_ic_menu_share_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_ic_star_black_16dp.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_ic_star_black_36dp.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_ic_star_black_48dp.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_ic_star_half_black_16dp.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_ic_star_half_black_36dp.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_ic_star_half_black_48dp.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_list_divider_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_list_focused_holo.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_list_longpressed_holo.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_list_pressed_holo_dark.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_list_pressed_holo_light.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_list_selector_disabled_holo_dark.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_list_selector_disabled_holo_light.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_menu_hardkey_panel_mtrl_mult.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_popup_background_mtrl_mult.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_scrubber_control_off_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_scrubber_control_to_pressed_mtrl_000.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_scrubber_control_to_pressed_mtrl_005.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_scrubber_primary_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_scrubber_track_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_spinner_mtrl_am_alpha.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_switch_track_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_tab_indicator_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_text_select_handle_left_mtrl_dark.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_text_select_handle_left_mtrl_light.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_text_select_handle_middle_mtrl_dark.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_text_select_handle_middle_mtrl_light.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_text_select_handle_right_mtrl_dark.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_text_select_handle_right_mtrl_light.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_textfield_activated_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_textfield_default_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_textfield_search_activated_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_abc_textfield_search_default_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_common_google_signin_btn_icon_dark_normal_background.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_common_google_signin_btn_icon_light_normal_background.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_common_google_signin_btn_text_dark_normal_background.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_common_google_signin_btn_text_light_normal_background.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_googleg_disabled_color_18.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_googleg_standard_color_18.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_notification_bg_low_normal.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_notification_bg_low_pressed.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_notification_bg_normal.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_notification_bg_normal_pressed.9.png.flat
│   │   │   │   │       ├── drawable-mdpi-v4_notify_panel_notification_icon_bg.png.flat
│   │   │   │   │       ├── drawable-v21_abc_action_bar_item_background_material.xml.flat
│   │   │   │   │       ├── drawable-v21_abc_btn_colored_material.xml.flat
│   │   │   │   │       ├── drawable-v21_abc_dialog_material_background.xml.flat
│   │   │   │   │       ├── drawable-v21_abc_edit_text_material.xml.flat
│   │   │   │   │       ├── drawable-v21_abc_list_divider_material.xml.flat
│   │   │   │   │       ├── drawable-v21_notification_action_background.xml.flat
│   │   │   │   │       ├── drawable-v23_abc_control_background_material.xml.flat
│   │   │   │   │       ├── drawable-v24_ic_launcher_foreground.xml.flat
│   │   │   │   │       ├── drawable-watch-v20_abc_dialog_material_background.xml.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_ab_share_pack_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_btn_check_to_on_mtrl_000.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_btn_check_to_on_mtrl_015.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_btn_radio_to_on_mtrl_000.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_btn_radio_to_on_mtrl_015.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_btn_switch_to_on_mtrl_00001.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_btn_switch_to_on_mtrl_00012.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_cab_background_top_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_ic_commit_search_api_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_ic_menu_copy_mtrl_am_alpha.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_ic_menu_cut_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_ic_menu_paste_mtrl_am_alpha.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_ic_menu_selectall_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_ic_menu_share_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_ic_star_black_16dp.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_ic_star_black_36dp.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_ic_star_black_48dp.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_ic_star_half_black_16dp.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_ic_star_half_black_36dp.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_ic_star_half_black_48dp.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_list_divider_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_list_focused_holo.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_list_longpressed_holo.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_list_pressed_holo_dark.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_list_pressed_holo_light.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_list_selector_disabled_holo_dark.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_list_selector_disabled_holo_light.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_menu_hardkey_panel_mtrl_mult.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_popup_background_mtrl_mult.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_scrubber_control_off_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_scrubber_control_to_pressed_mtrl_000.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_scrubber_control_to_pressed_mtrl_005.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_scrubber_primary_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_scrubber_track_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_spinner_mtrl_am_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_switch_track_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_tab_indicator_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_text_select_handle_left_mtrl_dark.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_text_select_handle_left_mtrl_light.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_text_select_handle_middle_mtrl_dark.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_text_select_handle_middle_mtrl_light.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_text_select_handle_right_mtrl_dark.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_text_select_handle_right_mtrl_light.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_textfield_activated_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_textfield_default_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_textfield_search_activated_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_abc_textfield_search_default_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_common_full_open_on_phone.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_common_google_signin_btn_icon_dark_normal_background.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_common_google_signin_btn_icon_light_normal_background.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_common_google_signin_btn_text_dark_normal_background.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_common_google_signin_btn_text_light_normal_background.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_googleg_disabled_color_18.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_googleg_standard_color_18.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_notification_bg_low_normal.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_notification_bg_low_pressed.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_notification_bg_normal.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_notification_bg_normal_pressed.9.png.flat
│   │   │   │   │       ├── drawable-xhdpi-v4_notify_panel_notification_icon_bg.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_ab_share_pack_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_btn_check_to_on_mtrl_000.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_btn_check_to_on_mtrl_015.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_btn_radio_to_on_mtrl_000.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_btn_radio_to_on_mtrl_015.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_btn_switch_to_on_mtrl_00001.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_btn_switch_to_on_mtrl_00012.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_cab_background_top_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_ic_commit_search_api_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_ic_menu_copy_mtrl_am_alpha.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_ic_menu_cut_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_ic_menu_paste_mtrl_am_alpha.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_ic_menu_selectall_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_ic_menu_share_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_ic_star_black_16dp.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_ic_star_black_36dp.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_ic_star_black_48dp.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_ic_star_half_black_16dp.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_ic_star_half_black_36dp.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_ic_star_half_black_48dp.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_list_divider_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_list_focused_holo.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_list_longpressed_holo.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_list_pressed_holo_dark.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_list_pressed_holo_light.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_list_selector_disabled_holo_dark.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_list_selector_disabled_holo_light.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_menu_hardkey_panel_mtrl_mult.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_popup_background_mtrl_mult.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_scrubber_control_off_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_scrubber_control_to_pressed_mtrl_000.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_scrubber_control_to_pressed_mtrl_005.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_scrubber_primary_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_scrubber_track_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_spinner_mtrl_am_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_switch_track_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_tab_indicator_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_text_select_handle_left_mtrl_dark.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_text_select_handle_left_mtrl_light.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_text_select_handle_middle_mtrl_dark.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_text_select_handle_middle_mtrl_light.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_text_select_handle_right_mtrl_dark.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_text_select_handle_right_mtrl_light.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_textfield_activated_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_textfield_default_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_textfield_search_activated_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_abc_textfield_search_default_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_common_google_signin_btn_icon_dark_normal_background.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_common_google_signin_btn_icon_light_normal_background.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_common_google_signin_btn_text_dark_normal_background.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_common_google_signin_btn_text_light_normal_background.9.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_googleg_disabled_color_18.png.flat
│   │   │   │   │       ├── drawable-xxhdpi-v4_googleg_standard_color_18.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_btn_check_to_on_mtrl_000.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_btn_check_to_on_mtrl_015.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_btn_radio_to_on_mtrl_000.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_btn_radio_to_on_mtrl_015.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_btn_switch_to_on_mtrl_00001.9.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_btn_switch_to_on_mtrl_00012.9.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_ic_menu_copy_mtrl_am_alpha.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_ic_menu_cut_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_ic_menu_paste_mtrl_am_alpha.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_ic_menu_selectall_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_ic_menu_share_mtrl_alpha.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_ic_star_black_16dp.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_ic_star_black_36dp.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_ic_star_black_48dp.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_ic_star_half_black_16dp.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_ic_star_half_black_36dp.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_ic_star_half_black_48dp.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_scrubber_control_to_pressed_mtrl_000.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_scrubber_control_to_pressed_mtrl_005.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_spinner_mtrl_am_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_switch_track_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_tab_indicator_mtrl_alpha.9.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_text_select_handle_left_mtrl_dark.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_text_select_handle_left_mtrl_light.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_text_select_handle_right_mtrl_dark.png.flat
│   │   │   │   │       ├── drawable-xxxhdpi-v4_abc_text_select_handle_right_mtrl_light.png.flat
│   │   │   │   │       ├── drawable_abc_btn_borderless_material.xml.flat
│   │   │   │   │       ├── drawable_abc_btn_check_material.xml.flat
│   │   │   │   │       ├── drawable_abc_btn_check_material_anim.xml.flat
│   │   │   │   │       ├── drawable_abc_btn_default_mtrl_shape.xml.flat
│   │   │   │   │       ├── drawable_abc_btn_radio_material.xml.flat
│   │   │   │   │       ├── drawable_abc_btn_radio_material_anim.xml.flat
│   │   │   │   │       ├── drawable_abc_cab_background_internal_bg.xml.flat
│   │   │   │   │       ├── drawable_abc_cab_background_top_material.xml.flat
│   │   │   │   │       ├── drawable_abc_ic_ab_back_material.xml.flat
│   │   │   │   │       ├── drawable_abc_ic_arrow_drop_right_black_24dp.xml.flat
│   │   │   │   │       ├── drawable_abc_ic_clear_material.xml.flat
│   │   │   │   │       ├── drawable_abc_ic_go_search_api_material.xml.flat
│   │   │   │   │       ├── drawable_abc_ic_menu_overflow_material.xml.flat
│   │   │   │   │       ├── drawable_abc_ic_search_api_material.xml.flat
│   │   │   │   │       ├── drawable_abc_ic_voice_search_api_material.xml.flat
│   │   │   │   │       ├── drawable_abc_item_background_holo_dark.xml.flat
│   │   │   │   │       ├── drawable_abc_item_background_holo_light.xml.flat
│   │   │   │   │       ├── drawable_abc_list_selector_background_transition_holo_dark.xml.flat
│   │   │   │   │       ├── drawable_abc_list_selector_background_transition_holo_light.xml.flat
│   │   │   │   │       ├── drawable_abc_list_selector_holo_dark.xml.flat
│   │   │   │   │       ├── drawable_abc_list_selector_holo_light.xml.flat
│   │   │   │   │       ├── drawable_abc_ratingbar_indicator_material.xml.flat
│   │   │   │   │       ├── drawable_abc_ratingbar_material.xml.flat
│   │   │   │   │       ├── drawable_abc_ratingbar_small_material.xml.flat
│   │   │   │   │       ├── drawable_abc_seekbar_thumb_material.xml.flat
│   │   │   │   │       ├── drawable_abc_seekbar_tick_mark_material.xml.flat
│   │   │   │   │       ├── drawable_abc_seekbar_track_material.xml.flat
│   │   │   │   │       ├── drawable_abc_spinner_textfield_background_material.xml.flat
│   │   │   │   │       ├── drawable_abc_switch_thumb_material.xml.flat
│   │   │   │   │       ├── drawable_abc_tab_indicator_material.xml.flat
│   │   │   │   │       ├── drawable_abc_text_cursor_material.xml.flat
│   │   │   │   │       ├── drawable_abc_textfield_search_material.xml.flat
│   │   │   │   │       ├── drawable_abc_vector_test.xml.flat
│   │   │   │   │       ├── drawable_btn_checkbox_checked_mtrl.xml.flat
│   │   │   │   │       ├── drawable_btn_checkbox_checked_to_unchecked_mtrl_animation.xml.flat
│   │   │   │   │       ├── drawable_btn_checkbox_unchecked_mtrl.xml.flat
│   │   │   │   │       ├── drawable_btn_checkbox_unchecked_to_checked_mtrl_animation.xml.flat
│   │   │   │   │       ├── drawable_btn_radio_off_mtrl.xml.flat
│   │   │   │   │       ├── drawable_btn_radio_off_to_on_mtrl_animation.xml.flat
│   │   │   │   │       ├── drawable_btn_radio_on_mtrl.xml.flat
│   │   │   │   │       ├── drawable_btn_radio_on_to_off_mtrl_animation.xml.flat
│   │   │   │   │       ├── drawable_common_google_signin_btn_icon_dark.xml.flat
│   │   │   │   │       ├── drawable_common_google_signin_btn_icon_dark_focused.xml.flat
│   │   │   │   │       ├── drawable_common_google_signin_btn_icon_dark_normal.xml.flat
│   │   │   │   │       ├── drawable_common_google_signin_btn_icon_disabled.xml.flat
│   │   │   │   │       ├── drawable_common_google_signin_btn_icon_light.xml.flat
│   │   │   │   │       ├── drawable_common_google_signin_btn_icon_light_focused.xml.flat
│   │   │   │   │       ├── drawable_common_google_signin_btn_icon_light_normal.xml.flat
│   │   │   │   │       ├── drawable_common_google_signin_btn_text_dark.xml.flat
│   │   │   │   │       ├── drawable_common_google_signin_btn_text_dark_focused.xml.flat
│   │   │   │   │       ├── drawable_common_google_signin_btn_text_dark_normal.xml.flat
│   │   │   │   │       ├── drawable_common_google_signin_btn_text_disabled.xml.flat
│   │   │   │   │       ├── drawable_common_google_signin_btn_text_light.xml.flat
│   │   │   │   │       ├── drawable_common_google_signin_btn_text_light_focused.xml.flat
│   │   │   │   │       ├── drawable_common_google_signin_btn_text_light_normal.xml.flat
│   │   │   │   │       ├── drawable_ic_launcher_background.xml.flat
│   │   │   │   │       ├── drawable_marker_red.png.flat
│   │   │   │   │       ├── drawable_marker_skull.png.flat
│   │   │   │   │       ├── drawable_notification_bg.xml.flat
│   │   │   │   │       ├── drawable_notification_bg_low.xml.flat
│   │   │   │   │       ├── drawable_notification_icon_background.xml.flat
│   │   │   │   │       ├── drawable_notification_tile_bg.xml.flat
│   │   │   │   │       ├── drawable_tooltip_frame_dark.xml.flat
│   │   │   │   │       ├── drawable_tooltip_frame_light.xml.flat
│   │   │   │   │       ├── drawable_virus.jpg.flat
│   │   │   │   │       ├── interpolator_btn_checkbox_checked_mtrl_animation_interpolator_0.xml.flat
│   │   │   │   │       ├── interpolator_btn_checkbox_checked_mtrl_animation_interpolator_1.xml.flat
│   │   │   │   │       ├── interpolator_btn_checkbox_unchecked_mtrl_animation_interpolator_0.xml.flat
│   │   │   │   │       ├── interpolator_btn_checkbox_unchecked_mtrl_animation_interpolator_1.xml.flat
│   │   │   │   │       ├── interpolator_btn_radio_to_off_mtrl_animation_interpolator_0.xml.flat
│   │   │   │   │       ├── interpolator_btn_radio_to_on_mtrl_animation_interpolator_0.xml.flat
│   │   │   │   │       ├── interpolator_fast_out_slow_in.xml.flat
│   │   │   │   │       ├── layout-v21_notification_action.xml.flat
│   │   │   │   │       ├── layout-v21_notification_action_tombstone.xml.flat
│   │   │   │   │       ├── layout-v21_notification_template_custom_big.xml.flat
│   │   │   │   │       ├── layout-v21_notification_template_icon_group.xml.flat
│   │   │   │   │       ├── layout-v26_abc_screen_toolbar.xml.flat
│   │   │   │   │       ├── layout-watch-v20_abc_alert_dialog_button_bar_material.xml.flat
│   │   │   │   │       ├── layout-watch-v20_abc_alert_dialog_title_material.xml.flat
│   │   │   │   │       ├── layout_abc_action_bar_title_item.xml.flat
│   │   │   │   │       ├── layout_abc_action_bar_up_container.xml.flat
│   │   │   │   │       ├── layout_abc_action_menu_item_layout.xml.flat
│   │   │   │   │       ├── layout_abc_action_menu_layout.xml.flat
│   │   │   │   │       ├── layout_abc_action_mode_bar.xml.flat
│   │   │   │   │       ├── layout_abc_action_mode_close_item_material.xml.flat
│   │   │   │   │       ├── layout_abc_activity_chooser_view.xml.flat
│   │   │   │   │       ├── layout_abc_activity_chooser_view_list_item.xml.flat
│   │   │   │   │       ├── layout_abc_alert_dialog_button_bar_material.xml.flat
│   │   │   │   │       ├── layout_abc_alert_dialog_material.xml.flat
│   │   │   │   │       ├── layout_abc_alert_dialog_title_material.xml.flat
│   │   │   │   │       ├── layout_abc_cascading_menu_item_layout.xml.flat
│   │   │   │   │       ├── layout_abc_dialog_title_material.xml.flat
│   │   │   │   │       ├── layout_abc_expanded_menu_layout.xml.flat
│   │   │   │   │       ├── layout_abc_list_menu_item_checkbox.xml.flat
│   │   │   │   │       ├── layout_abc_list_menu_item_icon.xml.flat
│   │   │   │   │       ├── layout_abc_list_menu_item_layout.xml.flat
│   │   │   │   │       ├── layout_abc_list_menu_item_radio.xml.flat
│   │   │   │   │       ├── layout_abc_popup_menu_header_item_layout.xml.flat
│   │   │   │   │       ├── layout_abc_popup_menu_item_layout.xml.flat
│   │   │   │   │       ├── layout_abc_screen_content_include.xml.flat
│   │   │   │   │       ├── layout_abc_screen_simple.xml.flat
│   │   │   │   │       ├── layout_abc_screen_simple_overlay_action_mode.xml.flat
│   │   │   │   │       ├── layout_abc_screen_toolbar.xml.flat
│   │   │   │   │       ├── layout_abc_search_dropdown_item_icons_2line.xml.flat
│   │   │   │   │       ├── layout_abc_search_view.xml.flat
│   │   │   │   │       ├── layout_abc_select_dialog_material.xml.flat
│   │   │   │   │       ├── layout_abc_tooltip.xml.flat
│   │   │   │   │       ├── layout_activity_corona_map.xml.flat
│   │   │   │   │       ├── layout_activity_corona_map_all.xml.flat
│   │   │   │   │       ├── layout_activity_location.xml.flat
│   │   │   │   │       ├── layout_activity_main.xml.flat
│   │   │   │   │       ├── layout_activity_second.xml.flat
│   │   │   │   │       ├── layout_activity_temp.xml.flat
│   │   │   │   │       ├── layout_custom_dialog.xml.flat
│   │   │   │   │       ├── layout_item.xml.flat
│   │   │   │   │       ├── layout_location.xml.flat
│   │   │   │   │       ├── layout_map_info.xml.flat
│   │   │   │   │       ├── layout_notification_template_part_chronometer.xml.flat
│   │   │   │   │       ├── layout_notification_template_part_time.xml.flat
│   │   │   │   │       ├── layout_select_dialog_item_material.xml.flat
│   │   │   │   │       ├── layout_select_dialog_multichoice_material.xml.flat
│   │   │   │   │       ├── layout_select_dialog_singlechoice_material.xml.flat
│   │   │   │   │       ├── layout_support_simple_spinner_dropdown_item.xml.flat
│   │   │   │   │       ├── mipmap-anydpi-v26_ic_launcher.xml.flat
│   │   │   │   │       ├── mipmap-anydpi-v26_ic_launcher_round.xml.flat
│   │   │   │   │       ├── mipmap-hdpi_ic_launcher.png.flat
│   │   │   │   │       ├── mipmap-hdpi_ic_launcher_foreground.png.flat
│   │   │   │   │       ├── mipmap-hdpi_ic_launcher_round.png.flat
│   │   │   │   │       ├── mipmap-mdpi_ic_launcher.png.flat
│   │   │   │   │       ├── mipmap-mdpi_ic_launcher_foreground.png.flat
│   │   │   │   │       ├── mipmap-mdpi_ic_launcher_round.png.flat
│   │   │   │   │       ├── mipmap-xhdpi_ic_launcher.png.flat
│   │   │   │   │       ├── mipmap-xhdpi_ic_launcher_foreground.png.flat
│   │   │   │   │       ├── mipmap-xhdpi_ic_launcher_round.png.flat
│   │   │   │   │       ├── mipmap-xxhdpi_ic_launcher.png.flat
│   │   │   │   │       ├── mipmap-xxhdpi_ic_launcher_foreground.png.flat
│   │   │   │   │       ├── mipmap-xxhdpi_ic_launcher_round.png.flat
│   │   │   │   │       ├── mipmap-xxxhdpi_ic_launcher.png.flat
│   │   │   │   │       ├── mipmap-xxxhdpi_ic_launcher_foreground.png.flat
│   │   │   │   │       ├── mipmap-xxxhdpi_ic_launcher_round.png.flat
│   │   │   │   │       ├── raw_r.mp3.flat
│   │   │   │   │       ├── raw_soso.mp3.flat
│   │   │   │   │       ├── values-af_values-af.arsc.flat
│   │   │   │   │       ├── values-am_values-am.arsc.flat
│   │   │   │   │       ├── values-ar_values-ar.arsc.flat
│   │   │   │   │       ├── values-as_values-as.arsc.flat
│   │   │   │   │       ├── values-az_values-az.arsc.flat
│   │   │   │   │       ├── values-b+sr+Latn_values-b+sr+Latn.arsc.flat
│   │   │   │   │       ├── values-be_values-be.arsc.flat
│   │   │   │   │       ├── values-bg_values-bg.arsc.flat
│   │   │   │   │       ├── values-bn_values-bn.arsc.flat
│   │   │   │   │       ├── values-bs_values-bs.arsc.flat
│   │   │   │   │       ├── values-ca_values-ca.arsc.flat
│   │   │   │   │       ├── values-cs_values-cs.arsc.flat
│   │   │   │   │       ├── values-da_values-da.arsc.flat
│   │   │   │   │       ├── values-de_values-de.arsc.flat
│   │   │   │   │       ├── values-el_values-el.arsc.flat
│   │   │   │   │       ├── values-en-rAU_values-en-rAU.arsc.flat
│   │   │   │   │       ├── values-en-rCA_values-en-rCA.arsc.flat
│   │   │   │   │       ├── values-en-rGB_values-en-rGB.arsc.flat
│   │   │   │   │       ├── values-en-rIN_values-en-rIN.arsc.flat
│   │   │   │   │       ├── values-en-rXC_values-en-rXC.arsc.flat
│   │   │   │   │       ├── values-es-rUS_values-es-rUS.arsc.flat
│   │   │   │   │       ├── values-es_values-es.arsc.flat
│   │   │   │   │       ├── values-et_values-et.arsc.flat
│   │   │   │   │       ├── values-eu_values-eu.arsc.flat
│   │   │   │   │       ├── values-fa_values-fa.arsc.flat
│   │   │   │   │       ├── values-fi_values-fi.arsc.flat
│   │   │   │   │       ├── values-fr-rCA_values-fr-rCA.arsc.flat
│   │   │   │   │       ├── values-fr_values-fr.arsc.flat
│   │   │   │   │       ├── values-gl_values-gl.arsc.flat
│   │   │   │   │       ├── values-gu_values-gu.arsc.flat
│   │   │   │   │       ├── values-h720dp-v13_values-h720dp-v13.arsc.flat
│   │   │   │   │       ├── values-hdpi-v4_values-hdpi-v4.arsc.flat
│   │   │   │   │       ├── values-hi_values-hi.arsc.flat
│   │   │   │   │       ├── values-hr_values-hr.arsc.flat
│   │   │   │   │       ├── values-hu_values-hu.arsc.flat
│   │   │   │   │       ├── values-hy_values-hy.arsc.flat
│   │   │   │   │       ├── values-in_values-in.arsc.flat
│   │   │   │   │       ├── values-is_values-is.arsc.flat
│   │   │   │   │       ├── values-it_values-it.arsc.flat
│   │   │   │   │       ├── values-iw_values-iw.arsc.flat
│   │   │   │   │       ├── values-ja_values-ja.arsc.flat
│   │   │   │   │       ├── values-ka_values-ka.arsc.flat
│   │   │   │   │       ├── values-kk_values-kk.arsc.flat
│   │   │   │   │       ├── values-km_values-km.arsc.flat
│   │   │   │   │       ├── values-kn_values-kn.arsc.flat
│   │   │   │   │       ├── values-ko_values-ko.arsc.flat
│   │   │   │   │       ├── values-ky_values-ky.arsc.flat
│   │   │   │   │       ├── values-land_values-land.arsc.flat
│   │   │   │   │       ├── values-large-v4_values-large-v4.arsc.flat
│   │   │   │   │       ├── values-ldltr-v21_values-ldltr-v21.arsc.flat
│   │   │   │   │       ├── values-lo_values-lo.arsc.flat
│   │   │   │   │       ├── values-lt_values-lt.arsc.flat
│   │   │   │   │       ├── values-lv_values-lv.arsc.flat
│   │   │   │   │       ├── values-mk_values-mk.arsc.flat
│   │   │   │   │       ├── values-ml_values-ml.arsc.flat
│   │   │   │   │       ├── values-mn_values-mn.arsc.flat
│   │   │   │   │       ├── values-mr_values-mr.arsc.flat
│   │   │   │   │       ├── values-ms_values-ms.arsc.flat
│   │   │   │   │       ├── values-my_values-my.arsc.flat
│   │   │   │   │       ├── values-nb_values-nb.arsc.flat
│   │   │   │   │       ├── values-ne_values-ne.arsc.flat
│   │   │   │   │       ├── values-night-v8_values-night-v8.arsc.flat
│   │   │   │   │       ├── values-nl_values-nl.arsc.flat
│   │   │   │   │       ├── values-or_values-or.arsc.flat
│   │   │   │   │       ├── values-pa_values-pa.arsc.flat
│   │   │   │   │       ├── values-pl_values-pl.arsc.flat
│   │   │   │   │       ├── values-port_values-port.arsc.flat
│   │   │   │   │       ├── values-pt-rBR_values-pt-rBR.arsc.flat
│   │   │   │   │       ├── values-pt-rPT_values-pt-rPT.arsc.flat
│   │   │   │   │       ├── values-pt_values-pt.arsc.flat
│   │   │   │   │       ├── values-ro_values-ro.arsc.flat
│   │   │   │   │       ├── values-ru_values-ru.arsc.flat
│   │   │   │   │       ├── values-si_values-si.arsc.flat
│   │   │   │   │       ├── values-sk_values-sk.arsc.flat
│   │   │   │   │       ├── values-sl_values-sl.arsc.flat
│   │   │   │   │       ├── values-sq_values-sq.arsc.flat
│   │   │   │   │       ├── values-sr_values-sr.arsc.flat
│   │   │   │   │       ├── values-sv_values-sv.arsc.flat
│   │   │   │   │       ├── values-sw600dp-v13_values-sw600dp-v13.arsc.flat
│   │   │   │   │       ├── values-sw_values-sw.arsc.flat
│   │   │   │   │       ├── values-ta_values-ta.arsc.flat
│   │   │   │   │       ├── values-te_values-te.arsc.flat
│   │   │   │   │       ├── values-th_values-th.arsc.flat
│   │   │   │   │       ├── values-tl_values-tl.arsc.flat
│   │   │   │   │       ├── values-tr_values-tr.arsc.flat
│   │   │   │   │       ├── values-uk_values-uk.arsc.flat
│   │   │   │   │       ├── values-ur_values-ur.arsc.flat
│   │   │   │   │       ├── values-uz_values-uz.arsc.flat
│   │   │   │   │       ├── values-v16_values-v16.arsc.flat
│   │   │   │   │       ├── values-v17_values-v17.arsc.flat
│   │   │   │   │       ├── values-v18_values-v18.arsc.flat
│   │   │   │   │       ├── values-v21_values-v21.arsc.flat
│   │   │   │   │       ├── values-v22_values-v22.arsc.flat
│   │   │   │   │       ├── values-v23_values-v23.arsc.flat
│   │   │   │   │       ├── values-v24_values-v24.arsc.flat
│   │   │   │   │       ├── values-v25_values-v25.arsc.flat
│   │   │   │   │       ├── values-v26_values-v26.arsc.flat
│   │   │   │   │       ├── values-v28_values-v28.arsc.flat
│   │   │   │   │       ├── values-vi_values-vi.arsc.flat
│   │   │   │   │       ├── values-watch-v20_values-watch-v20.arsc.flat
│   │   │   │   │       ├── values-watch-v21_values-watch-v21.arsc.flat
│   │   │   │   │       ├── values-xlarge-v4_values-xlarge-v4.arsc.flat
│   │   │   │   │       ├── values-zh-rCN_values-zh-rCN.arsc.flat
│   │   │   │   │       ├── values-zh-rHK_values-zh-rHK.arsc.flat
│   │   │   │   │       ├── values-zh-rTW_values-zh-rTW.arsc.flat
│   │   │   │   │       ├── values-zu_values-zu.arsc.flat
│   │   │   │   │       └── values_values.arsc.flat
│   │   │   │   └── symbol-table-with-package
│   │   │   │       └── debug
│   │   │   │           └── package-aware-r.txt
│   │   │   ├── shader_assets
│   │   │   │   └── debug
│   │   │   │       └── compileDebugShaders
│   │   │   │           └── out
│   │   │   ├── signing_config
│   │   │   │   └── debug
│   │   │   │       └── out
│   │   │   │           └── signing-config.json
│   │   │   ├── stripped_native_libs
│   │   │   │   └── debug
│   │   │   │       └── out
│   │   │   ├── symbols
│   │   │   │   └── debug
│   │   │   │       └── R.txt
│   │   │   ├── tmp
│   │   │   │   └── manifest
│   │   │   │       └── androidTest
│   │   │   │           └── debug
│   │   │   ├── transforms
│   │   │   │   └── dexBuilder
│   │   │   │       └── debug
│   │   │   │           ├── 0
│   │   │   │           │   ├── androidx
│   │   │   │           │   │   ├── activity
│   │   │   │           │   │   │   ├── R$attr.dex
│   │   │   │           │   │   │   ├── R$color.dex
│   │   │   │           │   │   │   ├── R$dimen.dex
│   │   │   │           │   │   │   ├── R$drawable.dex
│   │   │   │           │   │   │   ├── R$id.dex
│   │   │   │           │   │   │   ├── R$integer.dex
│   │   │   │           │   │   │   ├── R$layout.dex
│   │   │   │           │   │   │   ├── R$string.dex
│   │   │   │           │   │   │   ├── R$style.dex
│   │   │   │           │   │   │   ├── R$styleable.dex
│   │   │   │           │   │   │   └── R.dex
│   │   │   │           │   │   ├── appcompat
│   │   │   │           │   │   │   ├── R$anim.dex
│   │   │   │           │   │   │   ├── R$attr.dex
│   │   │   │           │   │   │   ├── R$bool.dex
│   │   │   │           │   │   │   ├── R$color.dex
│   │   │   │           │   │   │   ├── R$dimen.dex
│   │   │   │           │   │   │   ├── R$drawable.dex
│   │   │   │           │   │   │   ├── R$id.dex
│   │   │   │           │   │   │   ├── R$integer.dex
│   │   │   │           │   │   │   ├── R$interpolator.dex
│   │   │   │           │   │   │   ├── R$layout.dex
│   │   │   │           │   │   │   ├── R$string.dex
│   │   │   │           │   │   │   ├── R$style.dex
│   │   │   │           │   │   │   ├── R$styleable.dex
│   │   │   │           │   │   │   ├── R.dex
│   │   │   │           │   │   │   └── resources
│   │   │   │           │   │   │       ├── R$attr.dex
│   │   │   │           │   │   │       ├── R$color.dex
│   │   │   │           │   │   │       ├── R$dimen.dex
│   │   │   │           │   │   │       ├── R$drawable.dex
│   │   │   │           │   │   │       ├── R$id.dex
│   │   │   │           │   │   │       ├── R$integer.dex
│   │   │   │           │   │   │       ├── R$layout.dex
│   │   │   │           │   │   │       ├── R$string.dex
│   │   │   │           │   │   │       ├── R$style.dex
│   │   │   │           │   │   │       ├── R$styleable.dex
│   │   │   │           │   │   │       └── R.dex
│   │   │   │           │   │   ├── arch
│   │   │   │           │   │   │   └── core
│   │   │   │           │   │   │       └── R.dex
│   │   │   │           │   │   ├── constraintlayout
│   │   │   │           │   │   │   └── widget
│   │   │   │           │   │   │       ├── R$attr.dex
│   │   │   │           │   │   │       ├── R$id.dex
│   │   │   │           │   │   │       ├── R$styleable.dex
│   │   │   │           │   │   │       └── R.dex
│   │   │   │           │   │   ├── core
│   │   │   │           │   │   │   ├── R$attr.dex
│   │   │   │           │   │   │   ├── R$color.dex
│   │   │   │           │   │   │   ├── R$dimen.dex
│   │   │   │           │   │   │   ├── R$drawable.dex
│   │   │   │           │   │   │   ├── R$id.dex
│   │   │   │           │   │   │   ├── R$integer.dex
│   │   │   │           │   │   │   ├── R$layout.dex
│   │   │   │           │   │   │   ├── R$string.dex
│   │   │   │           │   │   │   ├── R$style.dex
│   │   │   │           │   │   │   ├── R$styleable.dex
│   │   │   │           │   │   │   └── R.dex
│   │   │   │           │   │   ├── cursoradapter
│   │   │   │           │   │   │   └── R.dex
│   │   │   │           │   │   ├── customview
│   │   │   │           │   │   │   ├── R$attr.dex
│   │   │   │           │   │   │   ├── R$color.dex
│   │   │   │           │   │   │   ├── R$dimen.dex
│   │   │   │           │   │   │   ├── R$drawable.dex
│   │   │   │           │   │   │   ├── R$id.dex
│   │   │   │           │   │   │   ├── R$integer.dex
│   │   │   │           │   │   │   ├── R$layout.dex
│   │   │   │           │   │   │   ├── R$string.dex
│   │   │   │           │   │   │   ├── R$style.dex
│   │   │   │           │   │   │   ├── R$styleable.dex
│   │   │   │           │   │   │   └── R.dex
│   │   │   │           │   │   ├── documentfile
│   │   │   │           │   │   │   └── R.dex
│   │   │   │           │   │   ├── drawerlayout
│   │   │   │           │   │   │   ├── R$attr.dex
│   │   │   │           │   │   │   ├── R$color.dex
│   │   │   │           │   │   │   ├── R$dimen.dex
│   │   │   │           │   │   │   ├── R$drawable.dex
│   │   │   │           │   │   │   ├── R$id.dex
│   │   │   │           │   │   │   ├── R$integer.dex
│   │   │   │           │   │   │   ├── R$layout.dex
│   │   │   │           │   │   │   ├── R$string.dex
│   │   │   │           │   │   │   ├── R$style.dex
│   │   │   │           │   │   │   ├── R$styleable.dex
│   │   │   │           │   │   │   └── R.dex
│   │   │   │           │   │   ├── fragment
│   │   │   │           │   │   │   ├── R$attr.dex
│   │   │   │           │   │   │   ├── R$color.dex
│   │   │   │           │   │   │   ├── R$dimen.dex
│   │   │   │           │   │   │   ├── R$drawable.dex
│   │   │   │           │   │   │   ├── R$id.dex
│   │   │   │           │   │   │   ├── R$integer.dex
│   │   │   │           │   │   │   ├── R$layout.dex
│   │   │   │           │   │   │   ├── R$string.dex
│   │   │   │           │   │   │   ├── R$style.dex
│   │   │   │           │   │   │   ├── R$styleable.dex
│   │   │   │           │   │   │   └── R.dex
│   │   │   │           │   │   ├── interpolator
│   │   │   │           │   │   │   └── R.dex
│   │   │   │           │   │   ├── legacy
│   │   │   │           │   │   │   └── coreutils
│   │   │   │           │   │   │       ├── R$attr.dex
│   │   │   │           │   │   │       ├── R$color.dex
│   │   │   │           │   │   │       ├── R$dimen.dex
│   │   │   │           │   │   │       ├── R$drawable.dex
│   │   │   │           │   │   │       ├── R$id.dex
│   │   │   │           │   │   │       ├── R$integer.dex
│   │   │   │           │   │   │       ├── R$layout.dex
│   │   │   │           │   │   │       ├── R$string.dex
│   │   │   │           │   │   │       ├── R$style.dex
│   │   │   │           │   │   │       ├── R$styleable.dex
│   │   │   │           │   │   │       └── R.dex
│   │   │   │           │   │   ├── lifecycle
│   │   │   │           │   │   │   ├── R.dex
│   │   │   │           │   │   │   ├── livedata
│   │   │   │           │   │   │   │   ├── R.dex
│   │   │   │           │   │   │   │   └── core
│   │   │   │           │   │   │   │       └── R.dex
│   │   │   │           │   │   │   └── viewmodel
│   │   │   │           │   │   │       └── R.dex
│   │   │   │           │   │   ├── loader
│   │   │   │           │   │   │   ├── R$attr.dex
│   │   │   │           │   │   │   ├── R$color.dex
│   │   │   │           │   │   │   ├── R$dimen.dex
│   │   │   │           │   │   │   ├── R$drawable.dex
│   │   │   │           │   │   │   ├── R$id.dex
│   │   │   │           │   │   │   ├── R$integer.dex
│   │   │   │           │   │   │   ├── R$layout.dex
│   │   │   │           │   │   │   ├── R$string.dex
│   │   │   │           │   │   │   ├── R$style.dex
│   │   │   │           │   │   │   ├── R$styleable.dex
│   │   │   │           │   │   │   └── R.dex
│   │   │   │           │   │   ├── localbroadcastmanager
│   │   │   │           │   │   │   └── R.dex
│   │   │   │           │   │   ├── print
│   │   │   │           │   │   │   └── R.dex
│   │   │   │           │   │   ├── savedstate
│   │   │   │           │   │   │   └── R.dex
│   │   │   │           │   │   ├── vectordrawable
│   │   │   │           │   │   │   ├── R$attr.dex
│   │   │   │           │   │   │   ├── R$color.dex
│   │   │   │           │   │   │   ├── R$dimen.dex
│   │   │   │           │   │   │   ├── R$drawable.dex
│   │   │   │           │   │   │   ├── R$id.dex
│   │   │   │           │   │   │   ├── R$integer.dex
│   │   │   │           │   │   │   ├── R$layout.dex
│   │   │   │           │   │   │   ├── R$string.dex
│   │   │   │           │   │   │   ├── R$style.dex
│   │   │   │           │   │   │   ├── R$styleable.dex
│   │   │   │           │   │   │   ├── R.dex
│   │   │   │           │   │   │   └── animated
│   │   │   │           │   │   │       ├── R$attr.dex
│   │   │   │           │   │   │       ├── R$color.dex
│   │   │   │           │   │   │       ├── R$dimen.dex
│   │   │   │           │   │   │       ├── R$drawable.dex
│   │   │   │           │   │   │       ├── R$id.dex
│   │   │   │           │   │   │       ├── R$integer.dex
│   │   │   │           │   │   │       ├── R$layout.dex
│   │   │   │           │   │   │       ├── R$string.dex
│   │   │   │           │   │   │       ├── R$style.dex
│   │   │   │           │   │   │       ├── R$styleable.dex
│   │   │   │           │   │   │       └── R.dex
│   │   │   │           │   │   ├── versionedparcelable
│   │   │   │           │   │   │   └── R.dex
│   │   │   │           │   │   └── viewpager
│   │   │   │           │   │       ├── R$attr.dex
│   │   │   │           │   │       ├── R$color.dex
│   │   │   │           │   │       ├── R$dimen.dex
│   │   │   │           │   │       ├── R$drawable.dex
│   │   │   │           │   │       ├── R$id.dex
│   │   │   │           │   │       ├── R$integer.dex
│   │   │   │           │   │       ├── R$layout.dex
│   │   │   │           │   │       ├── R$string.dex
│   │   │   │           │   │       ├── R$style.dex
│   │   │   │           │   │       ├── R$styleable.dex
│   │   │   │           │   │       └── R.dex
│   │   │   │           │   └── com
│   │   │   │           │       ├── example
│   │   │   │           │       │   └── coronaMapProject
│   │   │   │           │       │       ├── BuildConfig.dex
│   │   │   │           │       │       ├── CoronaLocation.dex
│   │   │   │           │       │       ├── CoronaLocationNearAlertService$1.dex
│   │   │   │           │       │       ├── CoronaLocationNearAlertService$MyBinder.dex
│   │   │   │           │       │       ├── CoronaLocationNearAlertService$MyLocationListener.dex
│   │   │   │           │       │       ├── CoronaLocationNearAlertService.dex
│   │   │   │           │       │       ├── CoronaMapActivity$1.dex
│   │   │   │           │       │       ├── CoronaMapActivity$MyLocation.dex
│   │   │   │           │       │       ├── CoronaMapActivity.dex
│   │   │   │           │       │       ├── CoronaMapAllActivity$1.dex
│   │   │   │           │       │       ├── CoronaMapAllActivity$MyLocation.dex
│   │   │   │           │       │       ├── CoronaMapAllActivity.dex
│   │   │   │           │       │       ├── CoronoLocationActivity$LocationAdapter.dex
│   │   │   │           │       │       ├── CoronoLocationActivity.dex
│   │   │   │           │       │       ├── GpsTracker.dex
│   │   │   │           │       │       ├── HttpHandler.dex
│   │   │   │           │       │       ├── Item.dex
│   │   │   │           │       │       ├── MainActivity$HttpTask.dex
│   │   │   │           │       │       ├── MainActivity.dex
│   │   │   │           │       │       ├── MyFirebaseMessagingService$1.dex
│   │   │   │           │       │       ├── MyFirebaseMessagingService.dex
│   │   │   │           │       │       ├── R$anim.dex
│   │   │   │           │       │       ├── R$attr.dex
│   │   │   │           │       │       ├── R$bool.dex
│   │   │   │           │       │       ├── R$color.dex
│   │   │   │           │       │       ├── R$dimen.dex
│   │   │   │           │       │       ├── R$drawable.dex
│   │   │   │           │       │       ├── R$id.dex
│   │   │   │           │       │       ├── R$integer.dex
│   │   │   │           │       │       ├── R$interpolator.dex
│   │   │   │           │       │       ├── R$layout.dex
│   │   │   │           │       │       ├── R$mipmap.dex
│   │   │   │           │       │       ├── R$raw.dex
│   │   │   │           │       │       ├── R$string.dex
│   │   │   │           │       │       ├── R$style.dex
│   │   │   │           │       │       ├── R$styleable.dex
│   │   │   │           │       │       ├── R.dex
│   │   │   │           │       │       ├── SecondActivity$ItemAdapter$1$1.dex
│   │   │   │           │       │       ├── SecondActivity$ItemAdapter$1.dex
│   │   │   │           │       │       ├── SecondActivity$ItemAdapter.dex
│   │   │   │           │       │       ├── SecondActivity$ItemAsync$1.dex
│   │   │   │           │       │       ├── SecondActivity$ItemAsync.dex
│   │   │   │           │       │       ├── SecondActivity.dex
│   │   │   │           │       │       └── Temp.dex
│   │   │   │           │       └── google
│   │   │   │           │           ├── android
│   │   │   │           │           │   └── gms
│   │   │   │           │           │       ├── ads_identifier
│   │   │   │           │           │       │   └── R.dex
│   │   │   │           │           │       ├── base
│   │   │   │           │           │       │   ├── R$attr.dex
│   │   │   │           │           │       │   ├── R$color.dex
│   │   │   │           │           │       │   ├── R$drawable.dex
│   │   │   │           │           │       │   ├── R$id.dex
│   │   │   │           │           │       │   ├── R$string.dex
│   │   │   │           │           │       │   ├── R$styleable.dex
│   │   │   │           │           │       │   └── R.dex
│   │   │   │           │           │       ├── common
│   │   │   │           │           │       │   ├── R$integer.dex
│   │   │   │           │           │       │   ├── R$string.dex
│   │   │   │           │           │       │   └── R.dex
│   │   │   │           │           │       ├── maps
│   │   │   │           │           │       │   ├── R$attr.dex
│   │   │   │           │           │       │   ├── R$id.dex
│   │   │   │           │           │       │   ├── R$styleable.dex
│   │   │   │           │           │       │   └── R.dex
│   │   │   │           │           │       ├── measurement
│   │   │   │           │           │       │   ├── api
│   │   │   │           │           │       │   │   └── R.dex
│   │   │   │           │           │       │   └── sdk
│   │   │   │           │           │       │       ├── R.dex
│   │   │   │           │           │       │       └── api
│   │   │   │           │           │       │           └── R.dex
│   │   │   │           │           │       ├── measurement_base
│   │   │   │           │           │       │   └── R.dex
│   │   │   │           │           │       ├── stats
│   │   │   │           │           │       │   └── R.dex
│   │   │   │           │           │       └── tasks
│   │   │   │           │           │           └── R.dex
│   │   │   │           │           └── firebase
│   │   │   │           │               ├── R$attr.dex
│   │   │   │           │               ├── R$color.dex
│   │   │   │           │               ├── R$dimen.dex
│   │   │   │           │               ├── R$drawable.dex
│   │   │   │           │               ├── R$id.dex
│   │   │   │           │               ├── R$integer.dex
│   │   │   │           │               ├── R$layout.dex
│   │   │   │           │               ├── R$string.dex
│   │   │   │           │               ├── R$style.dex
│   │   │   │           │               ├── R$styleable.dex
│   │   │   │           │               ├── R.dex
│   │   │   │           │               ├── analytics
│   │   │   │           │               │   └── connector
│   │   │   │           │               │       └── R.dex
│   │   │   │           │               ├── firebase_analytics
│   │   │   │           │               │   └── R.dex
│   │   │   │           │               ├── firebase_core
│   │   │   │           │               │   └── R.dex
│   │   │   │           │               ├── iid
│   │   │   │           │               │   ├── R.dex
│   │   │   │           │               │   └── internal
│   │   │   │           │               │       └── R.dex
│   │   │   │           │               ├── measurement
│   │   │   │           │               │   └── R.dex
│   │   │   │           │               ├── measurement_impl
│   │   │   │           │               │   └── R.dex
│   │   │   │           │               └── messaging
│   │   │   │           │                   ├── R$string.dex
│   │   │   │           │                   └── R.dex
│   │   │   │           └── __content__.json
│   │   │   └── validate_signing_config
│   │   │       └── debug
│   │   │           └── out
│   │   ├── outputs
│   │   │   ├── apk
│   │   │   │   └── debug
│   │   │   │       ├── app-debug.apk
│   │   │   │       └── output.json
│   │   │   └── logs
│   │   │       └── manifest-merger-debug-report.txt
│   │   └── tmp
│   │       └── compileDebugJavaWithJavac
│   ├── build.gradle
│   ├── google-services.json
│   ├── libs
│   ├── proguard-rules.pro
│   └── src
│       ├── androidTest
│       │   └── java
│       │       └── com
│       │           └── example
│       │               └── coronaMapProject
│       │                   └── ExampleInstrumentedTest.java
│       ├── debug
│       │   └── res
│       │       └── values
│       │           └── google_maps_api.xml
│       ├── main
│       │   ├── AndroidManifest.xml
│       │   ├── ic_launcher-web.png
│       │   ├── java
│       │   │   └── com
│       │   │       └── example
│       │   │           └── coronaMapProject
│       │   │               ├── CoronaLocation.java
│       │   │               ├── CoronaLocationNearAlertService.java
│       │   │               ├── CoronaMapActivity.java
│       │   │               ├── CoronaMapAllActivity.java
│       │   │               ├── CoronoLocationActivity.java
│       │   │               ├── GpsTracker.java
│       │   │               ├── HttpHandler.java
│       │   │               ├── Item.java
│       │   │               ├── MainActivity.java
│       │   │               ├── MyFirebaseMessagingService.java
│       │   │               ├── SecondActivity.java
│       │   │               └── Temp.java
│       │   └── res
│       │       ├── drawable
│       │       │   ├── ic_launcher_background.xml
│       │       │   ├── marker_red.png
│       │       │   ├── marker_skull.png
│       │       │   └── virus.jpg
│       │       ├── drawable-v24
│       │       │   └── ic_launcher_foreground.xml
│       │       ├── layout
│       │       │   ├── activity_corona_map.xml
│       │       │   ├── activity_corona_map_all.xml
│       │       │   ├── activity_location.xml
│       │       │   ├── activity_main.xml
│       │       │   ├── activity_second.xml
│       │       │   ├── activity_temp.xml
│       │       │   ├── item.xml
│       │       │   ├── location.xml
│       │       │   └── map_info.xml
│       │       ├── mipmap-anydpi-v26
│       │       │   ├── ic_launcher.xml
│       │       │   └── ic_launcher_round.xml
│       │       ├── mipmap-hdpi
│       │       │   ├── ic_launcher.png
│       │       │   ├── ic_launcher_foreground.png
│       │       │   └── ic_launcher_round.png
│       │       ├── mipmap-mdpi
│       │       │   ├── ic_launcher.png
│       │       │   ├── ic_launcher_foreground.png
│       │       │   └── ic_launcher_round.png
│       │       ├── mipmap-xhdpi
│       │       │   ├── ic_launcher.png
│       │       │   ├── ic_launcher_foreground.png
│       │       │   └── ic_launcher_round.png
│       │       ├── mipmap-xxhdpi
│       │       │   ├── ic_launcher.png
│       │       │   ├── ic_launcher_foreground.png
│       │       │   └── ic_launcher_round.png
│       │       ├── mipmap-xxxhdpi
│       │       │   ├── ic_launcher.png
│       │       │   ├── ic_launcher_foreground.png
│       │       │   └── ic_launcher_round.png
│       │       ├── raw
│       │       │   ├── r.mp3
│       │       │   └── soso.mp3
│       │       └── values
│       │           ├── colors.xml
│       │           ├── ic_launcher_background.xml
│       │           ├── strings.xml
│       │           └── styles.xml
│       ├── release
│       │   └── res
│       │       └── values
│       │           └── google_maps_api.xml
│       └── test
│           └── java
│               └── com
│                   └── example
│                       └── coronaMapProject
│                           └── ExampleUnitTest.java
├── build.gradle
├── coronaMapProject.iml
├── gradle
│   └── wrapper
│       ├── gradle-wrapper.jar
│       └── gradle-wrapper.properties
├── gradle.properties
├── gradlew
├── gradlew.bat
├── local.properties
└── settings.gradle
```