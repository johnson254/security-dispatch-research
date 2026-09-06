# Product Research: WalkieFleet + iConvNet (Inrico) APK

**Date:** 2026-07-22  
**Goal:** Inform naming + feature set for a new security-dispatch PoC platform built on/around WalkieFleet.

---

## 1. iConvNet APK — decoded (offline, no install)

**APK details**
- Package: `com.iconvnet.ptt`
- App name: **iConvNet** (launch activity: `com.inrico.iconvnet.activity.LoadingActivity`)
- Version: `3.1.067` (versionCode 41067)
- Min SDK: 21, Target SDK: 35
- Split APKs: base + `config.arm64_v8a` + `config.en` (English) + `config.mdpi`
- Native libs (arm64-v8a): `libBugly.so`, `libFFProducerUnit_arm64-v8a.so`, `libGVoiceUnit_arm64-v8a.so`, `libInricoMedia.so`, `libJni_wgs2gcj.so` (GCJ-02 coordinate system), `libMediaStreamUnit_arm64-v8a.so`
- Hardware keys bound: `com.tdtech.permission.PTT_KEY`, `FUNCTION_KEY`, `AUDIO_RECORD_KEY`, `IMP_KEY`, `MEDIA_RECORD_KEY`, `CAMERA_KEY`

### 1.1 Activities / Screens (full list, 120+ activities)

**Core communication**
- `LoadingActivity` — splash/loading
- `HomeActivity` — main screen
- `MenuActivity` — bottom nav / menu
- `CallDetailActivity`, `CalllogActivity`, `GroupCalllogActivity`, `NearestCallLogActivity`
- `ContactsActivity`, `GroupListActivity`, `GroupMembersActivity`, `GroupsActivity`
- `ConversationsActivity`, `MessageListActivity`, `MotoConversationsActivity`
- `SendTextActivity`, `PreDefMsgListActivity`
- `DialerActivity`, `QuickDialSelectActivity`, `OneTouchDialSettingsActivity`

**PTT / Voice**
- `CallActivity` (duplex)
- `TempGroupCallUiActivity`
- `PttLockScreenActivity`, `MiddleScreenPttLockScreenActivity`, `P177ScreenPttLockScreenActivity`
- `PttAutoTestActivity`

**Video / Camera / Surveillance**
- `CaptureActivity`, `PhotoActivity`, `PhotoDetailActivity`, `GalleryActivity`
- `VideoPlayActivity`
- `LiveVideoForwardActivity`, `LiveVideoGroupCallActivity`, `LiveVideoSupervisorActivity`, `LiveVideoUploadActivity`
- `RemoteCamListActivity`, `RemoteCamPreviewActivity`
- `UnionVideoSettingsActivity`, `VideoForwardActivity`

**DMR (radio integration)**
- `DmrActivity`, `ChannelInfoEditActivity`, `PocDmrParamActivity`
- `PD01MainActivity`, `PD01CallKeyboardActivity`, `PD01ChannelInfoActivity`, `PD01ContactInfoActivity`, `PD01CreateContactActivity`, `PD01McuUpdateActivity`, `PD01ModifyChannelActivity`, `PD01MotoInfoActivity`, `PD01RecordFilterActivity`, `PD01RecordHistoryActivity`, `PD01RecordMenuActivity`, `PD01ChatActivity`
- `DmrMapActivity`
- `GatewayGroupsActivity`

**NFC / Patrol / Guard Tour**
- `NfcActivity`
- `PatrolTaskActivity`, `PatrolTaskDetailActivity`, `PatrolTaskSettingsActivity`, `InspectionActivity`
- `Patrol2DepartmentTaskActivity`, `Patrol2ExceptionActivity`, `Patrol2MediaAddActivity`, `Patrol2OfflineDataActivity`, `Patrol2PointCollectActivity`, `Patrol2PointCollectListActivity`, `Patrol2ScheduleDetailActivity`, `Patrol2SpecialEventActivity`
- `PatrolRecordActivity`

**GPS / Map / Location**
- `MapActivity`, `OfflineMapActivity`, `ChooseLocationActivity`
- `P177ShowLocationActivity`

**SOS / Emergency / Alarms**
- `ProtectAlarmSettingsActivity`
- `StaticAlarmSettingsActivity`
- `ManDownSettingsActivity`
- `AloneWorkerSettingsActivity`
- `WarnAfterManDownActivity`, `WarnPreAloneWorkerActivity`, `WarnAfterAloneWorkerActivity`, `WarnAfterStaticAlarmActivity`
- `SosSecureSettingsActivity`

**AI Events**
- `AIEventsActivity`, `AIEventDetailActivity`

**Visitor Management / Gates**
- `VisitActivity`, `VisitAptDetailActivity`, `VisitCheckInActivity`, `VisitCheckRecordsActivity`, `VisitEditInfoActivity`, `VisitManualActivity`, `VisitTempRecordsActivity`

**Event Reporting / Job Tickets**
- `EventReportActivity`, `EventReportDetailActivity`, `EventDraftActivity`
- `JobTicketsActivity`, `JobTicketDetailActivity`, `JobTicketRefuseActivity`

**Broadcast**
- `CreateBroadcastActivity`, `BroadcastMessageActivity`, `HistoryBroadcastActivity`
- `P177BroadcastListActivity`, `P177MessageListActivity`

**Media / Recording**
- `AudioRecordActivity`, `Mp3RecordHistoryActivity`, `Mp3RecordHistoryDetailActivity`
- `CallRecordActivity`
- `FloatVideoRecordService`, `FloatConfService`, `FloatTempCallService`

**Live streaming / Video**
- `LiveVideoForwardActivity`, `LiveVideoGroupCallActivity`, `LiveVideoSupervisorActivity`, `LiveVideoUploadActivity`
- `FloatLiveVideoForwardService`, `FloatLiveVideoUploadService`

**Settings / Configuration**
- `SettingsActivity`, `SystemSettingActivity`, `NotificationManagerActivity`, `NotificationTypeManagerActivity`
- `FunctionalSettingsActivity`, `ShortcutSettingActivity`, `TerminalFunctionsActivity`
- `T60SettingsActivity`, `P177SettingsActivity`, `SmallScreenSettingsActivity`
- `VersionSettingsActivity`, `SetHeartBeatActivity`, `SetLogIpActivity`
- `ModifyUserInfoActivity`, `ModifyMemberInfoActivity`, `ModifyPasswordActivity`
- `UserInfomationActivity`
- `PrivacyPolicyShowActivity`
- `ZhifayiBleBindSettings`

**Dispatcher**
- `DispatcherActivity`

**QR / Barcode**
- `QRScanActivity`, `BarcodeScanningActivity`, `ScannerActivity`

**Conference / Group call**
- `ConfActivity`

**Bluetooth**
- `BluetoothConnectActivity`

**Other**
- `AddCompanyActivity`, `SelectCompanyActivity`
- `ContactsActivity`
- `GalleryActivity`
- `OfflineMapActivity`
- `PowerAutoTestActivity`, `PttAutoTestActivity`, `PluginTestActivity`
- `StorageDisplayActivity`
- `SignatureActivity`
- `ShowQrCodeActivity`, `ShowWebActivity`
- `MiddleScreenLauncherActivity`, `MiddleScreenShortcutActivity`, `MiddleScreenShortcutKeySetActivity`, `MiddleScreenShortcutSystemToolsActivity`
- `P177MainMenuActivity`, `P177LoadingActivity`
- `PrevenLossHomeActivity`
- `ZhifayiActivity`, `ZfyMiniActivity`
- `AddUsersToTempActivity`, `ChooseMembersToTempActivity`, `SelectAssistantActivity`, `QuickCallContactSelectActivity`
- `ChooseAddressActivity`

### 1.2 Services (background)
- `KeepAliveService` — keepalive/heartbeat
- `ScreenShotService` — screenshot capture
- `DmrTcpService` — DMR radio TCP connection
- `FloatCallService` — floating call UI
- `FloatConfService` — floating conference UI
- `FloatTempCallService` — floating temp group call
- `FloatVideoRecordService` — floating video recording
- `FloatLiveVideoForwardService` — floating live video forward
- `FloatLiveVideoUploadService` — floating live video upload
- `MediaInitializer` — media init
- `HyteraKeyService` — Hytera radio key service
- `FileInitializer` — file init
- `ZhifayiInitializer` — Zfy (植牙仪? dental implant?) init
- `IntervalAlarm` — interval alarm

### 1.3 Receivers (system event hooks)
- `DeviceStateReceiver` — device state changes (boot, power, storage, etc.)
- `LaunchReceiver` — app launch/receiver
- `HeadsetButtonReceiver` — headset button events
- `GalaxyXCoverReceiverManager` — Samsung rugged device keys
- `HyteraReceiverManager` — Hytera DMR radio keys

### 1.4 Permissions (full list, grouped)

**Audio/Video/Camera**
- `RECORD_AUDIO`, `MODIFY_AUDIO_SETTINGS`, `CAMERA`, `FOREGROUND_SERVICE_MICROPHONE`, `FOREGROUND_SERVICE_CAMERA`, `FOREGROUND_SERVICE_MEDIA_PROJECTION`, `FOREGROUND_SERVICE_MEDIA_PLAYBACK`

**Location (heavy — background + foreground)**
- `ACCESS_FINE_LOCATION`, `ACCESS_COARSE_LOCATION`, `ACCESS_HIGH_LOCATION`, `ACCESS_BACKGROUND_LOCATION`, `ACCESS_LOCATION_EXTRA_COMMANDS`, `ACCESS_MEDIA_LOCATION`

**Network / Connectivity**
- `INTERNET`, `ACCESS_WIFI_STATE`, `ACCESS_NETWORK_STATE`, `CHANGE_WIFI_STATE`, `CHANGE_NETWORK_STATE`, `BLUETOOTH`, `BLUETOOTH_ADMIN`, `BLUETOOTH_SCAN`, `BLUETOOTH_ADVERTISE`, `BLUETOOTH_CONNECT`

**System / Device control (heavy — this is a kiosk/rugged app)**
- `WRITE_SETTINGS`, `READ_SETTINGS`, `EXPAND_STATUS_BAR`, `DISABLE_KEYGUARD`, `REQUEST_IGNORE_BATTERY_OPTIMIZATIONS`, `SCHEDULE_EXACT_ALARM`, `RECEIVE_BOOT_COMPLETED`, `WAKE_LOCK`, `DEVICE_POWER`, `VIBRATE`, `SYSTEM_ALERT_WINDOW`, `SYSTEM_OVERLAY_WINDOW`, `FOREGROUND_SERVICE`, `FOREGROUND_SERVICE_LOCATION`, `POST_NOTIFICATIONS`, `ACCESS_NOTIFICATION_POLICY`

**App management (self-update + install)**
- `DOWNLOAD_WITHOUT_NOTIFICATION`, `GRANT_RUNTIME_PERMISSIONS`, `REVOKE_RUNTIME_PERMISSIONS`, `GET_RUNTIME_PERMISSIONS`
- `com.iconvnet.ptt.conference.providers.downloads.permission.*` (custom download manager)

**Phone / SMS**
- `CALL_PHONE`, `READ_PHONE_STATE`, `SEND_SMS`

**Storage**
- `READ_EXTERNAL_STORAGE`, `WRITE_EXTERNAL_STORAGE`, `READ_MEDIA_IMAGES`, `READ_MEDIA_VIDEO`, `READ_MEDIA_AUDIO`

**Hardware-specific**
- `NFC`, `android.hardware.nfc`
- `INJECT_EVENTS` (synthetic input)
- `USB_PERMISSION`
- `READ_LOGS`, `GET_TASKS`, `REORDER_TASKS`, `KILL_BACKGROUND_PROCESSES` (system-level)

**Launcher integration**
- `com.android.launcher.permission.INSTALL_SHORTCUT`, `UNINSTALL_SHORTCUT`, `READ_SETTINGS` (for launcher1/2/3)

**Proprietary hardware key permissions**
- `com.tdtech.permission.PTT_KEY`
- `com.tdtech.permission.FUNCTION_KEY`
- `com.tdtech.permission.AUDIO_RECORD_KEY`
- `com.tdtech.permission.IMP_KEY`
- `com.tdtech.permission.MEDIA_RECORD_KEY`
- `com.tdtech.permission.CAMERA_KEY`

**External service binding**
- `com.veclink.vecsipsimple.BIND_POC_SERVICE` (SIP/VoIP binding)

### 1.5 Key string resources (feature evidence)

**Multi-brand white-label**
- 30+ `app_name_*` strings: `acoms`, `agt`, `alson`, `aselsan`, `chaveirim`, `constell`, `critical`, `criticomm`, `ecar`, `fengyi`, `fushan`, `grs`, `hawkeye`, `hear`, `hzzq`, `iconvnet`, `itp`, `kenwood`, `moto`, `neutral`, `new`, `onecomm`, `powertrack`, `preven_loss`, `pttpro`, `radioip`, `retech`, `rigidex`, `sdcl`, `smart_talk`, `stele`, `stratigos`, `talkplus`, `talkptt`, `ten_a80`, `ten_a802`, `tigo`, `titanes`, `ttadv`, `whch`, `widget`, `xiangzhougongan`, `xiom`

**Core features (from string keys)**
- `ptt`, `call`, `voice_call`, `video_call`, `video_broadcast`, `audio_meeting`
- `call_log_*`, `call_records`, `group_call`, `temp_call`
- `dmr_*` (channel, zone, color code, slot, call type, analog/digital, repeater, talk around, frequency)
- `sos_*`, `sos_type_alone_worker`, `sos_type_man_down`, `sos_type_static`, `sos_type_bt`, `sos_type_group`
- `alone_worker_*`, `man_down_*`, `static_alarm_*`
- `nfc_*`, `patrol_*`, `inspection`, `work_nfc`
- `map_*`, `locate_*`, `gps_*`
- `broadcast_*` (alarm time, select group, select member, freq, loop, once, timezone)
- `visit_*` (check in, check out, visitor records, appointment, ID card, driver's license, vehicle)
- `event_report_*`, `event_draft`, `job_ticket_*`, `work_order_*`
- `ai_event_*` (camera, license plate, person name, similarity, flag yes/no, real-time)
- `live_video_forward_*`, `video_upload_*`
- `remote_cam`, `surveillance_camera`
- `audio_record_*`, `video_record_*`, `preview_*`, `playback_*`
- `settings_*`, `terminal_*`, `functional_settings`
- `shortcut_*`, `custom_buttons`
- `fisheye_*` (180/360), `hard_decode`, `smart_detect`

**Map providers supported**
- `com.autonavi.minimap` (Amap/高德)
- `com.baidu.BaiduMap` (百度)
- `com.tencent.map` (腾讯)
- `com.google.android.apps.maps` (Google)
- `com.waze`
- `ru.yandex.yandexmaps` (Yandex)
- `com.nhn.android.nmap` (Naver)
- `ru.dublgis.dgismobile` (2GIS)
- `com.here.app.maps` (HERE)
- `net.osmand` (OSM)
- `com.mapswithme.maps.pro` (MAPS.ME)
- `com.sygic.aura` (Sygic)
- `com.grabtaxi.passenger` (Grab)
- `com.mmi.navic` (MiTAC)
- `com.mmi.maps` (Magellan)

**Hardware key intents (device-specific)**
- `com.airbus.pmr.action.PTT_START/STOP` — Airbus PMR radio
- `com.android.PTT.ACTION_DOWN/UP`, `SOS_DOWN` — generic Android PTT key
- `com.android.common.PTT.down/up` — common PTT
- `com.android.cusKey.*` — custom keys (back, camera, F1-F6, menu)
- `com.android.extKey.*` — extended keys (P1-P3, one/two/three, voice)
- `com.tdtech.permission.*` — TDTECH radio keys
- `com.veclink.vecsipsimple.BIND_POC_SERVICE` — Veclink SIP/PoC

---

## 2. WalkieFleet — exact product language (from walkiefleet.com)

### Homepage tagline
> "Professional Voice and Video Broadband Push-to-Talk Solution"  
> Keywords from meta: PoC, DMR, Push to Talk, Walkie Talkie, MCPTT, Dispatch Software, software for Excera, software for Hytera, software for Kirisun, PTT platform, PTT Android.

### Features page — exact copy
- **Voice PTT** — "Voice calls are made like on a professional two-way radio. Press the button to start talking immediately without confirmation from the receiving party. Available for individual and group communication."
- **Video PTT** — "Walkie Talkie communication powered by video transmitted together with the voice. Send a real-time video of the surroundings by pushing the video transmit button. Available for individual and group communication."
- **Messenger** — "WalkieFleet messenger allows real-time exchange of text messages, images and files. The messenger is available for both private conversations between individual users and communication within the group."
- **Location Tracking** — "WalkieFleet has GPS tracking capability to determine the location of the fleet member. Two options available: single request or time-lapse request with periodic location updates at regular intervals. A location request can be applied to both a single user and a group. WalkieFleet supports Google Map and OpenStreetMap for location tracking."
- **Over the Air Programming** — "The WalkieFleet dispatcher can remotely modify user configuration settings and send them updates."
- **Emergency Processing** — "Emergency and Man Down alerts, emergency receivers, high priority emergency call, on-screen SOS button in the mobile client are defined in customizable emergency profiles. An emergency report in the dispatch console shows detailed information about all emergencies for a given time interval."
- **Redundancy Server** — "Increase your system reliability by setting up a backup WalkieFleet server. All Networks, users and groups are automatically replicated from the master to the backup server. All clients are automatically transferred to the backup server in case of the master failure."
- **Voice and Video Recording** — "All voice and video calls are recorded at WalkieFleet Walkie Talkie Server. Each voice conversation is recorded into mp3 file. Video calls are recorded into mkv format."

### PC Dispatch Console page — exact copy (the *real* feature list)
> "Main functionality available in Dispatch Console:
> - Control over Multiple Communication Networks
> - Voice PTT Calls
> - Video PTT Calls
> - Emergency Processing
> - Dynamic Groups
> - Message Exchange (Text, Image, Files)
> - Location Tracking
> - **Geofencing**
> - **Guard Tour**
> - **OTAP - Over the Air Programming**
> - **User Block/Unblock**
> - **Event Logging**
> - Location History Tracks
> - Reporting Tools"
>
> "Unlike the mobile client, **dispatch application can receive and make several calls at the same time**."

---

## 3. Feature comparison — iConvNet vs WalkieFleet

| Feature | iConvNet (Inrico) | WalkieFleet |
|---|---|---|
| Voice PTT | ✅ (PTT key hardware + soft) | ✅ |
| Video PTT / Video call | ✅ | ✅ |
| DMR radio integration | ✅ (DmrActivity, DmrTcpService, PD01*) | ✅ (DMR Integration page) |
| SIP / VoIP | ✅ (Veclink bind) | ✅ |
| GPS / Map tracking | ✅ (MapActivity, 12 map providers) | ✅ (Google + OSM) |
| NFC guard tour / patrol | ✅ (NfcActivity, Patrol2*, InspectionActivity) | ✅ (Guard Tour listed) |
| Geofencing | ✅ (terminal_voice_fence) | ✅ |
| SOS / Man Down / Lone Worker | ✅ (3 alarm types, settings screens) | ✅ (Emergency Processing) |
| Event reporting | ✅ (EventReport*) | ✅ (Event Logging) |
| Job tickets / Work orders | ✅ (JobTickets*, WorkOrderActivity) | ❓ |
| Visitor management | ✅ (Visit* activities, check-in/out) | ❓ |
| AI events (weapon/face/LPR) | ✅ (AIEvents*, AIEventDetail*) | ❓ |
| Broadcast / messaging | ✅ (broadcast_*, messenger) | ✅ (Messenger) |
| Group management | ✅ (GroupsActivity, GroupMembers) | ✅ (Dynamic Groups) |
| Remote camera / surveillance | ✅ (RemoteCam*, FloatVideo*) | ✅ (Video PTT) |
| Live streaming | ✅ (LiveVideo*) | ✅ |
| Video upload | ✅ (video_upload*) | ✅ (Video Recording) |
| Recording | ✅ (AudioRecord*, Mp3Record*) | ✅ (MP3 + MKV) |
| OTAP / remote config | ✅ (OTA implied, settings push) | ✅ |
| Multi-brand / white-label | ✅ (30+ app_name_* strings) | ❓ |
| Dispatch console | ✅ (DispatcherActivity) | ✅ (PC Dispatch Console) |
| Multi-call | ✅ | ✅ |
| Fisheye / PTZ camera | ✅ (fisheye_*, camera control) | ❓ |
| Bluetooth peripheral | ✅ (BluetoothConnectActivity, BLE) | ❓ |
| Offline map | ✅ (OfflineMapActivity) | ❌ |
| QR / Barcode scanning | ✅ (QRScanActivity, BarcodeScanningActivity) | ❓ |
| Patrol task distribution | ✅ (Patrol2Schedule*, JobTickets*) | ❓ |
| Auto clock-in | ✅ (auto_clockin) | ❓ |
| Anti-mistouch lock | ✅ (anti_mistouch_lock*) | ❓ |
| Middle screen / kiosk mode | ✅ (MiddleScreen*) | ❓ |
| Custom button mapping | ✅ (custom_buttons, shortcut_*) | ❓ |

---

## 4. Naming direction (informed by actual product language)

WalkieFleet's brand vocabulary:
- "Walkie" (walkie-talkie, radio heritage)
- "Fleet" (fleet management, vehicles/people)
- "PoC" (Push-to-Talk over Cellular)
- "Dispatch Console"
- "Guard Tour"
- "Geofencing"
- "Redundancy Server"

iConvNet / Inrico brand vocabulary:
- "iConvNet" = their platform name
- "iconv" = icon + v (video?)
- "Patrol2" = their second-gen patrol system
- "P177" = a device model code
- "PD01" = another device model
- "Zfy" = their third-party dental/medical integration
- "Zhifayi" = another integration
- "PrevenLoss" = loss-prevention branding
- "T60" = terminal/settings framework
- Multi-brand white-label: they sell the same APK rebranded to 30+ security companies (AGT, Alson, Aselsan, Caltta, Hawkeye, Kenwood, Moto, Powertrack, Rigidex, Smart Talk, Stele, TITANES, Talkplus, etc.)

### Naming angles that fit the actual product
1. **Fleet/guard heritage:** e.g. `FleetGuard`, `FleetWatch`, `FleetDesk`
2. **Patrol/task heritage:** e.g. `PatrolDesk`, `PatrolFlow`, `PatrolOps`
3. **Gate/dispatch heritage:** e.g. `GateDesk`, `GateLog`, `GateOps`
4. **PTT/radio heritage:** e.g. `PTTDesk`, `PTTHub`, `PTTFlow`
5. **Combination:** `PatrolDesk` (patrol + dispatcher desk), `GateFlow` (gate + workflow), `FleetDesk` (fleet + desk)

### Top candidates (grounded in real product language)
1. **PatrolDesk** — matches both WalkieFleet's "Guard Tour" + iConvNet's `Patrol2` + our "dispatch console/desk" angle. Clean, professional.
2. **FleetDesk** — matches WalkieFleet's "fleet" + our "dispatch console/desk" angle.
3. **GateDesk** — matches the user's "gates and dispatchers" requirement + "desk" = dispatcher control room.
4. **FleetLog** — fleet + logging/audit (WalkieFleet has "Event Logging", we own the log layer).
5. **PatrolOps** — patrol + operations, short, punchy.

---

## 5. Key findings

### What iConvNet proves is possible on Android
- **NFC guard tour + patrol** with point collection, schedule, offline data, exception reporting
- **DMR + PoC dual-mode** on the same device
- **Multi-brand white-label** from a single APK (30+ skins)
- **Heavy hardware integration**: PTT keys, function keys, SOS key, camera key, headset buttons, Bluetooth peripherals
- **SOS types**: alone worker, man-down, static alarm, SOS button, Bluetooth SOS
- **Visitor management** with check-in/out, appointment, ID scanning
- **AI event detection** (weapon, face, license plate, similarity matching)
- **Live video forwarding** (supervisor view, group call, upload)
- **Offline maps**
- **Fisheye / PTZ camera control**
- **QR / barcode scanning**
- **Job tickets / task distribution** (work orders)
- **Auto clock-in**

### Gaps / opportunities (what neither product does well, or what we can own)
- NFC guard tour with **sequential order + GPS proximity anti-cheat** — iConvNet has patrol but not explicit sequential-order enforcement
- **Gate control** (open/close, log entry/exit) — not seen in either app
- **AI analytics** on recordings (both record, but neither has on-device weapon/face/LPR)
- **Multi-tenant isolation** at org level
- **Open-source / own-branded** product (both closed-source)
- **Tauri dispatcher desktop** (iConvNet has Android dispatcher; WalkieFleet has Windows-only PC console)

---

## 6. Open questions / TODO
- [ ] Full screen-by-screen walkthrough of iConvNet (install on non-tethered test device, or use static analysis on layouts)
- [ ] Decode `resources.arsc` for string *values* (currently only have keys, not the actual localized text)
- [ ] Check `walkiefleet.com/pocdevices` and `/dmrintegration` pages
- [ ] Decompile DEX to see the actual Java/Kotlin code for AI event pipeline and patrol logic
- [ ] Ask Inrico for their reseller/white-label program (since they already do 30+ brands)
