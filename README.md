# dagger-demoð¡

![Daggerð¡](./assets/dagger.png)

---

Daggerã¯ãæ¥æ¬èªã«è¨³ãã¨ç­å£ã¨ããæå³ã§ãã  
ç±æ¥ã¯ç­å£ã®ããã«ä½¿ãåæãè¯ããã¼ã«ã ããã§ããã­ï¼ï¼ç¥ãããã©ãããï¼  
ã½ããã¦ã§ã¢ã®ãã«ãããã¹ããããã­ã¤ãè¡ãä¸é£ã®CI/CDãã¤ãã©ã¤ã³ããã¼ã¿ãã«ãªéçºã­ããã§ãã  

* å¬å¼  
  https://dagger.io/
* Github  
  https://github.com/dagger/dagger

---

## ãã¢ã®æµã
* ð¡ ã­ã¼ã«ã«ç°å¢ãæ§ç¯ãã
* ð¡ ãµã³ãã«ã¢ããªããã«ããã
* ð¡ ãµã³ãã«ã¢ããªãå®è¡ãã
* ð¡ ãµã³ãã«ã¢ããªã®ãã«ãå®ç¾©

---
# ãã¢ãè¡ã

## ð¡ ã­ã¼ã«ã«ç°å¢ãæ§ç¯ãã
Getting Started

https://docs.dagger.io/getting-started/

ã®æé ã«å¾ã£ã¦ã»ããã¢ãããããï¼â»Windowsç°å¢ï¼

https://docs.dagger.io/1200/local-dev/

```
Invoke-WebRequest -UseBasicParsing -Uri https://dl.dagger.io/dagger/install.ps1 | Invoke-Expression
```
ã»ããã¢ãããå®äºããã¨ä¸è¨ã¡ãã»ã¼ã¸ãè¡¨ç¤ºãããã
```
Thank You for downloading Dagger!

-----------------------------------------------------
Dagger has been saved at <YOUR HOME FOLDER>/dagger/
Please add dagger.exe to your PATH in order to use it
----------------------------------------------------
```
ããã§Windowsã®ã¦ã¼ã¶ã¼ç°å¢å¤æ°ï¼PATHï¼ã« 
dagger.exeãã»ããã¢ããããããã¹ãè¿½å ãã¦ã¿ã¼ããã«ï¼ãããã¯IDEï¼ãåèµ·åããã

## ð¡ ãµã³ãã«ã¢ããªããã«ããã
Githubãããµã³ãã«ãcloneããã

https://github.com/dagger/dagger

```
cd dagger
git checkout v0.2.8
```
ï¼â»ããèµ·åãã¦ãªããã°ï¼Docker Desktopãèµ·åãããï¼â»ã¡ãªãã¼ã¸ã§ã³ã¯4.7.1ï¼

ãµã³ãã«ã¢ããªãbuildããã
```
cd pkg/universe.dagger.io/examples/todoapp
dagger do build
```
å¤±æãããã0.2.9ãä»¥ä¸ã®ãã¼ã¸ã§ã³ãä½¿ãã¨æããã¾ãããï¼å¬å¼æé ã®ã¨ãããªã®ã«wï¼
```
failed to load plan: package "dagger.io" is incompatible with this version of dagger (requires 0.2.9 or newer). Run `dagger project update` to resolve this
```
æ°ãåãç´ãã¦ã¢ãããã¼ãããã
```
dagger project update
Project updated

dagger version
dagger 0.2.9 (4fc38dac) windows/amd64
```
ãªãã¨ãªãè¸é¨ããããã®ã§ä¸å¿cloneãããµã³ãã«ãåãã¼ã¸ã§ã³ã«ãã¦ããããã
```
git checkout v0.2.9
```
ãååº¦ããµã³ãã«ã¢ããªããã«ãããã
```
dagger do build
```
ï¼æ«ãå¾æ©ãããï¼ååå®è¡æã¯æã£ãããæéãããï¼ç´5åå¼±ç¨ï¼
```
[â] actions.test.script                          0.5s
[â] actions.deps                               197.9s
[â] client.filesystem."./".read                  1.0s
[â] actions.build.run.script                     0.7s
[â] actions.test                                 2.8s
[â] actions.build.run                           26.9s
[â] actions.build.contents                       0.2s
[â] client.filesystem."./_build".write           0.4s
```
ãã«ãæåï¼

ã­ã¼ã«ã«ç°å¢ã®ã³ã³ãããç¢ºèªããã¨daggerã®ã³ã³ãããå±ããã¨ãåããã¾ãã
```
docker ps
CONTAINER ID   IMAGE                   COMMAND       CREATED          STATUS          PORTS     NAMES           
d033d42ec2b2   moby/buildkit:v0.10.2   "buildkitd"   12 minutes ago   Up 12 minutes             dagger-buildkitd
```
ã¡ãªã¿ã«ããã  
Docker Desktopãèµ·åãã¦ãªãã¨ä¸è¨ã®ããã«å®è¡ã¨ã©ã¼ã«ãªãã¾ããï¼â»ãæ³¨æãã°ï¼
```
dagger do build
3:43PM ERR failed to run docker: exit status 1    output=Client:
 Context:    default
3:43PM ERR failed to run docker: exit status 1    output=Client:
 Context:    default
 Debug Mode: falseuildx (Docker Inc., v0.8.1)
 Plugins:: Docker Compose (Docker Inc., v2.3.3)
  buildx: Docker Buildx (Docker Inc., v0.8.1)
  compose: Docker Compose (Docker Inc., v2.3.3)
  scan: Docker Scan (Docker Inc., v0.17.0)
ERROR: error during connect: This error may indicate that the docker daemon is not running.: Get "http://%2F%2F.%2Fpipe%2Fdocker_engine/v1.24/info": open //./pipe/docker_engine: The system cannot find the file specified.
Server:pretty printing info
ERROR: error during connect: This error may indicate that the docker daemon is not running.: Get "http://%2F%2F.%2Fpipe%2Fdocker_engine/v1.24/info": open //./pipe/docker_engine: The system cannot find the file specified.
errors pretty printing info

3:43PM FTL unable to create client: exit status 1
```

## ð¡ ãµã³ãã«ã¢ããªãå®è¡ãã
ãã«ãæåããã¢ããªãå®è¡ããã
```
start _build/index.html
```
ã¡ããã¨ãã«ãåºæ¥ã¦ãã
![Daggerð¡](./assets/todoapp.png)

ãåãåº¦ããµã³ãã«ã¢ããªããã«ãããã
```
dagger do build
```
ãã¡ãéããï¼daggerããã¦ã³ã­ã¼ãï¼èµ·åæ¸ã¿ãªã®ã§ãããï¼
```
[â] actions.build.run.script                     0.1s
[â] actions.test.script                          0.1s
[â] actions.deps                                 1.1s
[â] client.filesystem."./".read                  0.2s
[â] actions.test                                 0.0s
[â] actions.build.run                            0.0s
[â] actions.build.contents                       0.0s
[â] client.filesystem."./_build".write           0.3s
```

## ð¡ ãµã³ãã«ã¢ããªã®ãã«ãå®ç¾©
ãµã³ãã«ã¢ããªã®ãã«ãå®ç¾©ãã¡ã¤ã«ãâããè¦ã¦ã¿ãã

> pkg/universe.dagger.io/examples/todoapp/todoapp.cue

GoogleãéçºããCUEè¨èªã¨ããç¬èªã®æ¸å¼ã§è¨è¿°ãã¦ããã®ãèå³æ·±ããï¼YAMLå°çããè±åºãããããããï¼

ãã ããä»»æã®ãã­ã°ã©ãã³ã°è¨èªï¼ã·ã§ã«ã¹ã¯ãªããããã©ï¼ã§ã¢ã¯ã·ã§ã³ãä½æãããã¨ãå¯è½ã

æ§æã¯AWSã®Codebuildã® `buildspec.yml` ã«ä¼¼ã¦ããå°è±¡ãåãããï¼ç¨éãåãã ããå½ããåã ãï¼

æ°ãã«CUEã®æ¸ãæ¹ãè¦ããå¿è¦ã¯ããããã©ãã©ã®ç°å¢ã§ãåãããã«ãã«ãã§ããã®ã¯ãããããã

ã­ã¼ã«ã«ã§è©¦ãã¦åãçµæã«ãªããã¨ãä¿è¨¼ãããã®ã¯ããããã

ãã¾ãæµè¡ãã°CI/CDã®ãã¼ã¿ããªãã£ãç¢ºä¿ããã­ãã¯ã¤ã³ãé¿ããããããï¼â»ç¾æç¹ã§æ­£å¼ãªãªã¼ã¹ææã¯æªå®ï¼

```
package todoapp

import (
	"dagger.io/dagger"
	"dagger.io/dagger/core"
	"universe.dagger.io/alpine"
	"universe.dagger.io/bash"
	"universe.dagger.io/docker"
	"universe.dagger.io/netlify"
)

dagger.#Plan & {
	_nodeModulesMount: "/src/node_modules": {
		dest:     "/src/node_modules"
		type:     "cache"
		contents: core.#CacheDir & {
			id: "todoapp-modules-cache"
		}

	}
	client: {
		filesystem: {
			"./": read: {
				contents: dagger.#FS
				exclude: [
					"README.md",
					"_build",
					"todoapp.cue",
					"node_modules",
				]
			}
			"./_build": write: contents: actions.build.contents.output
		}
		env: {
			APP_NAME:      string
			NETLIFY_TEAM:  string
			NETLIFY_TOKEN: dagger.#Secret
		}
	}
	actions: {
		deps: docker.#Build & {
			steps: [
				alpine.#Build & {
					packages: {
						bash: {}
						yarn: {}
						git: {}
					}
				},
				docker.#Copy & {
					contents: client.filesystem."./".read.contents
					dest:     "/src"
				},
				bash.#Run & {
					workdir: "/src"
					mounts: {
						"/cache/yarn": {
							dest:     "/cache/yarn"
							type:     "cache"
							contents: core.#CacheDir & {
								id: "todoapp-yarn-cache"
							}
						}
						_nodeModulesMount
					}
					script: contents: #"""
						yarn config set cache-folder /cache/yarn
						yarn install
						"""#
				},
			]
		}

		test: bash.#Run & {
			input:   deps.output
			workdir: "/src"
			mounts:  _nodeModulesMount
			script: contents: #"""
				yarn run test
				"""#
		}

		build: {
			run: bash.#Run & {
				input:   test.output
				mounts:  _nodeModulesMount
				workdir: "/src"
				script: contents: #"""
					yarn run build
					"""#
			}

			contents: core.#Subdir & {
				input: run.output.rootfs
				path:  "/src/build"
			}
		}

		deploy: netlify.#Deploy & {
			contents: build.contents.output
			site:     client.env.APP_NAME
			token:    client.env.NETLIFY_TOKEN
			team:     client.env.NETLIFY_TEAM
		}
	}
}
```
