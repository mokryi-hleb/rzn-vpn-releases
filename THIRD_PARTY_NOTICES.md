# Third-party components

The application uses unmodified official libXray Android binaries downloaded by `scripts/fetch_xray.py`.

- **libXray v26.10.17** — [source](https://github.com/XTLS/libXray/tree/v26.10.17), [MIT license](https://github.com/XTLS/libXray/blob/v26.10.17/LICENSE).
- **Xray-core**, pinned by that libXray release to `92ccc939aaf4` — [source](https://github.com/XTLS/Xray-core/tree/92ccc939aaf4), [Mozilla Public License 2.0](https://github.com/XTLS/Xray-core/blob/92ccc939aaf4/LICENSE).
- **Go runtime and gomobile** — [Go license](https://go.dev/LICENSE), [gomobile source and license](https://go.googlesource.com/mobile/).
- **AndroidX / Jetpack Compose**, including **graphics-shapes 1.0.1** — [source and licenses](https://android.googlesource.com/platform/frameworks/support/), Apache License 2.0.
- **Kotlin and kotlinx.coroutines** — [Kotlin](https://github.com/JetBrains/kotlin), [coroutines](https://github.com/Kotlin/kotlinx.coroutines), Apache License 2.0.
- **OkHttp 4.12.0 and Okio** — [source and license](https://github.com/square/okhttp/tree/parent-4.12.0), Apache License 2.0.

The `org.json` JVM dependency is used for compilation and tests; Android supplies its platform implementation at runtime. JUnit and MockWebServer are test-only dependencies.

Routing data is derived from [RunetFreedom GeoSite](https://github.com/runetfreedom/russia-blocked-geosite) and [RunetFreedom GeoIP](https://github.com/runetfreedom/russia-blocked-geoip), distributed through [russia-v2ray-rules-dat](https://github.com/runetfreedom/russia-v2ray-rules-dat). The upstream repositories use GNU GPL v3; the license text is included in `app/src/main/assets/licenses/runetfreedom-GPL-3.0.txt`.

The blocked-resource categories include [Re:filter](https://github.com/1andrevich/Re-filter-lists), Antifilter and Antifilter Community data; Russian domain categories include contributions from [v2fly/domain-list-community](https://github.com/v2fly/domain-list-community) and [runetfreedom/russia-domains-list](https://github.com/runetfreedom/russia-domains-list). See the upstream repositories for their data sources and attribution.

Only the categories listed in `geodata/sources.json` are retained. Their protobuf records are copied byte for byte, without changing domains, CIDRs or matching types. `scripts/fetch_geodata.py` contains the complete selection procedure and pins the source commit and SHA-256 checksums; the bundled `routing/manifest.json` records the selected-file checksums. Source releases remain available at the linked public repositories.
