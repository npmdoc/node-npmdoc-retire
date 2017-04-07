# api documentation for  [retire (v1.2.12)](https://github.com/RetireJS/retire.js#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-retire.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-retire) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-retire.svg)](https://travis-ci.org/npmdoc/node-npmdoc-retire)
#### Retire is a tool for detecting use of vulnerable libraries

[![NPM](https://nodei.co/npm/retire.png?downloads=true)](https://www.npmjs.com/package/retire)

[![apidoc](https://npmdoc.github.io/node-npmdoc-retire/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-retire_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-retire/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-retire/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-retire/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Erlend Oftedal",
        "email": "erlend@oftedal.no"
    },
    "bin": {
        "retire": "./bin/retire"
    },
    "bugs": {
        "url": "https://github.com/RetireJS/retire.js/issues"
    },
    "dependencies": {
        "commander": "2.5.x",
        "read-installed": "^4.0.3",
        "request": "~2.x.x",
        "walkdir": "0.0.7"
    },
    "description": "Retire is a tool for detecting use of vulnerable libraries",
    "devDependencies": {
        "jshint": "",
        "nodeunit": ""
    },
    "directories": {},
    "dist": {
        "shasum": "6f2b8d21afa3a4629dd3d28e3d63a389f7efac26",
        "tarball": "https://registry.npmjs.org/retire/-/retire-1.2.12.tgz"
    },
    "engines": {
        "node": ">= 0.10.0"
    },
    "homepage": "https://github.com/RetireJS/retire.js#readme",
    "main": "./lib/retire.js",
    "maintainers": [
        {
            "name": "eoftedal",
            "email": "erlend@oftedal.no"
        }
    ],
    "name": "retire",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/RetireJS/retire.js.git"
    },
    "scripts": {
        "test": "./test"
    },
    "version": "1.2.12"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module retire](#apidoc.module.retire)
1.  [function <span class="apidocSignatureSpan">retire.</span>check (component, version, repo)](#apidoc.element.retire.check)
1.  [function <span class="apidocSignatureSpan">retire.</span>isVulnerable (results)](#apidoc.element.retire.isVulnerable)
1.  [function <span class="apidocSignatureSpan">retire.</span>replaceVersion (jsRepoJsonAsText)](#apidoc.element.retire.replaceVersion)
1.  [function <span class="apidocSignatureSpan">retire.</span>scanFileContent (content, repo, hasher)](#apidoc.element.retire.scanFileContent)
1.  [function <span class="apidocSignatureSpan">retire.</span>scanFileName (fileName, repo)](#apidoc.element.retire.scanFileName)
1.  [function <span class="apidocSignatureSpan">retire.</span>scanNodeDependency (dependency, npmrepo)](#apidoc.element.retire.scanNodeDependency)
1.  [function <span class="apidocSignatureSpan">retire.</span>scanUri (uri, repo)](#apidoc.element.retire.scanUri)
1.  object <span class="apidocSignatureSpan">retire.</span>repo
1.  object <span class="apidocSignatureSpan">retire.</span>resolve
1.  object <span class="apidocSignatureSpan">retire.</span>scanner
1.  object <span class="apidocSignatureSpan">retire.</span>utils
1.  string <span class="apidocSignatureSpan">retire.</span>version

#### [module retire.repo](#apidoc.module.retire.repo)
1.  [function <span class="apidocSignatureSpan">retire.repo.</span>loadrepository (repoUrl, options)](#apidoc.element.retire.repo.loadrepository)
1.  [function <span class="apidocSignatureSpan">retire.repo.</span>loadrepositoryFromFile (filepath, options)](#apidoc.element.retire.repo.loadrepositoryFromFile)

#### [module retire.resolve](#apidoc.module.retire.resolve)
1.  [function <span class="apidocSignatureSpan">retire.resolve.</span>getNodeDependencies (path, limit)](#apidoc.element.retire.resolve.getNodeDependencies)
1.  [function <span class="apidocSignatureSpan">retire.resolve.</span>scanJsFiles (path)](#apidoc.element.retire.resolve.scanJsFiles)

#### [module retire.scanner](#apidoc.module.retire.scanner)
1.  [function <span class="apidocSignatureSpan">retire.scanner.</span>on (name, listener)](#apidoc.element.retire.scanner.on)
1.  [function <span class="apidocSignatureSpan">retire.scanner.</span>scanBowerFile (file, repo, options)](#apidoc.element.retire.scanner.scanBowerFile)
1.  [function <span class="apidocSignatureSpan">retire.scanner.</span>scanDependencies (dependencies, nodeRepo, options)](#apidoc.element.retire.scanner.scanDependencies)
1.  [function <span class="apidocSignatureSpan">retire.scanner.</span>scanJsFile (file, repo, options)](#apidoc.element.retire.scanner.scanJsFile)

#### [module retire.utils](#apidoc.module.retire.utils)
1.  [function <span class="apidocSignatureSpan">retire.utils.</span>detect (ar, fn)](#apidoc.element.retire.utils.detect)
1.  [function <span class="apidocSignatureSpan">retire.utils.</span>every (things, predicate)](#apidoc.element.retire.utils.every)
1.  [function <span class="apidocSignatureSpan">retire.utils.</span>extend (o, a)](#apidoc.element.retire.utils.extend)
1.  [function <span class="apidocSignatureSpan">retire.utils.</span>find (ar, fn)](#apidoc.element.retire.utils.find)
1.  [function <span class="apidocSignatureSpan">retire.utils.</span>flatten (e)](#apidoc.element.retire.utils.flatten)
1.  [function <span class="apidocSignatureSpan">retire.utils.</span>forwardEvent (emitter, event)](#apidoc.element.retire.utils.forwardEvent)
1.  [function <span class="apidocSignatureSpan">retire.utils.</span>log (options)](#apidoc.element.retire.utils.log)
1.  [function <span class="apidocSignatureSpan">retire.utils.</span>map (o, fn)](#apidoc.element.retire.utils.map)
1.  [function <span class="apidocSignatureSpan">retire.utils.</span>pick (p, keys)](#apidoc.element.retire.utils.pick)



# <a name="apidoc.module.retire"></a>[module retire](#apidoc.module.retire)

#### <a name="apidoc.element.retire.check"></a>[function <span class="apidocSignatureSpan">retire.</span>check (component, version, repo)](#apidoc.element.retire.check)
- description and source-code
```javascript
check = function (component, version, repo) {
	return check([{component: component, version: version}], repo);
}
```
- example usage
```shell
...
function scanBowerFile(file, repo, options) {
  if (options.ignore && shouldIgnorePath([file], options.ignore)) {
    return;
  }
  try {
    var bower = JSON.parse(fs.readFileSync(file));
    if (bower.version) {
      var results = retire.check(bower.name, bower.version, repo);
      printResults(file, results, options);
    }
  } catch (e) {
    log(options).warn('Could not parse file: ' + file);
  }
}
...
```

#### <a name="apidoc.element.retire.isVulnerable"></a>[function <span class="apidocSignatureSpan">retire.</span>isVulnerable (results)](#apidoc.element.retire.isVulnerable)
- description and source-code
```javascript
isVulnerable = function (results) {
	for (var r in results) {
		if (results[r].hasOwnProperty('vulnerabilities')) return true;
	}
	return false;
}
```
- example usage
```shell
...
  shasum.update(data);
  return shasum.digest('hex');
}
};

function printResults(file, results, options) {
removeIgnored(results, options.ignore);
if (!retire.isVulnerable(results) && !options.verbose) return;
var logger = log(options).info;
if (retire.isVulnerable(results)) {
  logger = log(options).warn;
  events.emit('vulnerable-dependency-found', {file: file, results: results});
} else {
  events.emit('dependency-found', {file: file, results: results});
}
...
```

#### <a name="apidoc.element.retire.replaceVersion"></a>[function <span class="apidocSignatureSpan">retire.</span>replaceVersion (jsRepoJsonAsText)](#apidoc.element.retire.replaceVersion)
- description and source-code
```javascript
replaceVersion = function (jsRepoJsonAsText) {
	return jsRepoJsonAsText.replace(/§§version§§/g, '[0-9][0-9.a-z_\\\\-]+');
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.retire.scanFileContent"></a>[function <span class="apidocSignatureSpan">retire.</span>scanFileContent (content, repo, hasher)](#apidoc.element.retire.scanFileContent)
- description and source-code
```javascript
scanFileContent = function (content, repo, hasher) {
	var result = scan(content, 'filecontent', repo);
	if (result.length === 0) {
		result = scan(content, 'filecontentreplace', repo, replacementMatch);
	}
	if (result.length === 0) {
		result = scanhash(hasher.sha1(content), repo);
	}
	return check(result, repo);
}
```
- example usage
```shell
...

function scanJsFile(file, repo, options) {
if (options.ignore && shouldIgnorePath([file], options.ignore)) {
  return;
}
var results = retire.scanFileName(file, repo);
if (!results || results.length === 0) {
  results = retire.scanFileContent(fs.readFileSync(file), repo, hash);
}
printResults(file, results, options);
}

function printParent(comp, options) {
if ('parent' in comp) printParent(comp.parent, options);
log(options).info(new Array(comp.level).join(' ') + (comp.parent ? String.fromCharCode(8627) + ' ' : '') + comp.component + ' ' +
comp.version);
...
```

#### <a name="apidoc.element.retire.scanFileName"></a>[function <span class="apidocSignatureSpan">retire.</span>scanFileName (fileName, repo)](#apidoc.element.retire.scanFileName)
- description and source-code
```javascript
scanFileName = function (fileName, repo) {
	var result = scan(fileName, 'filename', repo);
	return check(result, repo);
}
```
- example usage
```shell
...
}


function scanJsFile(file, repo, options) {
  if (options.ignore && shouldIgnorePath([file], options.ignore)) {
    return;
  }
  var results = retire.scanFileName(file, repo);
  if (!results || results.length === 0) {
    results = retire.scanFileContent(fs.readFileSync(file), repo, hash);
  }
  printResults(file, results, options);
}

function printParent(comp, options) {
...
```

#### <a name="apidoc.element.retire.scanNodeDependency"></a>[function <span class="apidocSignatureSpan">retire.</span>scanNodeDependency (dependency, npmrepo)](#apidoc.element.retire.scanNodeDependency)
- description and source-code
```javascript
scanNodeDependency = function (dependency, npmrepo) {
	if (!isDefined(dependency.version)) {
		console.warn('Missing version for ' + dependency.component + '. Need to run npm install ?');
		return [];
	}
	if (!isDefined(npmrepo[dependency.component])) return [];
	return check([dependency], npmrepo);
}
```
- example usage
```shell
...
}

function scanDependencies(dependencies, nodeRepo, options) {
for (var i in dependencies) {
  if (options.ignore && shouldIgnorePath([dependencies[i].component, toModulePath(dependencies[i])], options.ignore)) {
    continue;
  }
  results = retire.scanNodeDependency(dependencies[i], nodeRepo);
  if (retire.isVulnerable(results)) {
    events.emit('vulnerable-dependency-found', {results: results});
    var result = results[0]; //Only single scan here
    log(options).warn(result.component + ' ' + result.version + ' has known vulnerabilities: ' + printVulnerability(result, options
));
    if (result.parent) {
      printParent(result, options);
    }
...
```

#### <a name="apidoc.element.retire.scanUri"></a>[function <span class="apidocSignatureSpan">retire.</span>scanUri (uri, repo)](#apidoc.element.retire.scanUri)
- description and source-code
```javascript
scanUri = function (uri, repo) {
	var result = scan(uri, 'uri', repo);
	return check(result, repo);
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.retire.repo"></a>[module retire.repo](#apidoc.module.retire.repo)

#### <a name="apidoc.element.retire.repo.loadrepository"></a>[function <span class="apidocSignatureSpan">retire.repo.</span>loadrepository (repoUrl, options)](#apidoc.element.retire.repo.loadrepository)
- description and source-code
```javascript
loadrepository = function (repoUrl, options) {
    options = utils.extend(options, { process : retire.replaceVersion });
    if (options.nocache) {
        return loadJson(repoUrl, options);
    }
    return loadFromCache(repoUrl, options.cachedir, options);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.retire.repo.loadrepositoryFromFile"></a>[function <span class="apidocSignatureSpan">retire.repo.</span>loadrepositoryFromFile (filepath, options)](#apidoc.element.retire.repo.loadrepositoryFromFile)
- description and source-code
```javascript
loadrepositoryFromFile = function (filepath, options) {
    options = utils.extend(options, { process : retire.replaceVersion });
	return loadJsonFromFile(filepath, options);
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.retire.resolve"></a>[module retire.resolve](#apidoc.module.retire.resolve)

#### <a name="apidoc.element.retire.resolve.getNodeDependencies"></a>[function <span class="apidocSignatureSpan">retire.resolve.</span>getNodeDependencies (path, limit)](#apidoc.element.retire.resolve.getNodeDependencies)
- description and source-code
```javascript
getNodeDependencies = function (path, limit) {
	return getNodeDependencies(path, limit);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.retire.resolve.scanJsFiles"></a>[function <span class="apidocSignatureSpan">retire.resolve.</span>scanJsFiles (path)](#apidoc.element.retire.resolve.scanJsFiles)
- description and source-code
```javascript
scanJsFiles = function (path) {
	return scanJsFiles(path);
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.retire.scanner"></a>[module retire.scanner](#apidoc.module.retire.scanner)

#### <a name="apidoc.element.retire.scanner.on"></a>[function <span class="apidocSignatureSpan">retire.scanner.</span>on (name, listener)](#apidoc.element.retire.scanner.on)
- description and source-code
```javascript
on = function (name, listener) {
	events.on(name, listener);
}
```
- example usage
```shell
...
        } else {
            if (fs.existsSync(path.resolve(cachedir, cache[url].date + '.json'))) {
                fs.unlink(path.resolve(cachedir, cache[url].date + '.json'));
            }
        }
    }
    var events = new emitter();
    loadJson(url, options).on('done', function(data) {
        cache[url] = { date : now, file : now + '.json' };
        fs.writeFileSync(path.resolve(cachedir, cache[url].file), JSON.stringify(data), { encoding : 'utf8' });
        fs.writeFileSync(cacheIndex, JSON.stringify(cache), { encoding : 'utf8' });
        events.emit('done', data);
    }).on('stop', forward(events, 'stop'));
    return events;
}
...
```

#### <a name="apidoc.element.retire.scanner.scanBowerFile"></a>[function <span class="apidocSignatureSpan">retire.scanner.</span>scanBowerFile (file, repo, options)](#apidoc.element.retire.scanner.scanBowerFile)
- description and source-code
```javascript
scanBowerFile = function (file, repo, options) {
  return scanBowerFile(file, repo, options);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.retire.scanner.scanDependencies"></a>[function <span class="apidocSignatureSpan">retire.scanner.</span>scanDependencies (dependencies, nodeRepo, options)](#apidoc.element.retire.scanner.scanDependencies)
- description and source-code
```javascript
scanDependencies = function (dependencies, nodeRepo, options) {
	return scanDependencies(dependencies, nodeRepo, options);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.retire.scanner.scanJsFile"></a>[function <span class="apidocSignatureSpan">retire.scanner.</span>scanJsFile (file, repo, options)](#apidoc.element.retire.scanner.scanJsFile)
- description and source-code
```javascript
scanJsFile = function (file, repo, options) {
	return scanJsFile(file, repo, options);
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.retire.utils"></a>[module retire.utils](#apidoc.module.retire.utils)

#### <a name="apidoc.element.retire.utils.detect"></a>[function <span class="apidocSignatureSpan">retire.utils.</span>detect (ar, fn)](#apidoc.element.retire.utils.detect)
- description and source-code
```javascript
detect = function (ar, fn) {
	for(var i in ar) {
		if (fn(ar[i])) return ar[i];
	}
	return undefined;
}
```
- example usage
```shell
...
    }
    string += vulnerability.info.join(options.outputformat === 'clean' ? '\n' : ' ');
  });
  return string;
}

function shouldIgnorePath(fileSpecs, ignores) {
  return utils.detect(ignores.paths, function(i) {
    return utils.detect(fileSpecs, function(j) {
      return j.indexOf(i) === 0 || j.indexOf(path.resolve(i)) === 0 ;
    });
  });
}

function removeIgnored(results, ignores) {
...
```

#### <a name="apidoc.element.retire.utils.every"></a>[function <span class="apidocSignatureSpan">retire.utils.</span>every (things, predicate)](#apidoc.element.retire.utils.every)
- description and source-code
```javascript
every = function (things, predicate){
	return Object.keys(things)
		.map(function(k) { return predicate(k, things[k]) })
		.reduce(function(x,y) { return x && y }, true);
}
```
- example usage
```shell
...
    if (r.vulnerabilities.length === 0) delete r.vulnerabilities;
  });
}

function removeIgnoredVulnerabilitiesByIdentifier(identifiers, result) {
  result.vulnerabilities = result.vulnerabilities.filter(function(v) {
    if (!v.hasOwnProperty("identifiers")) return true;
    return !utils.every(identifiers, function(key, value) { return hasIdentifier(v, key, value); });
  });
}
function hasIdentifier(vulnerability, key, value) {
  if (!vulnerability.identifiers.hasOwnProperty(key)) return false;
  var identifier = vulnerability.identifiers[key];
  return Array.isArray(identifier) ? identifier.some(function(x) { return x === value; }) : identifier === value;
}
...
```

#### <a name="apidoc.element.retire.utils.extend"></a>[function <span class="apidocSignatureSpan">retire.utils.</span>extend (o, a)](#apidoc.element.retire.utils.extend)
- description and source-code
```javascript
extend = function (o, a) {
	var result = exports.pick(o, Object.keys(o));
	exports.map(a, function(v,k){ result[k] = v; });
	return result;
}
```
- example usage
```shell
...
        fs.writeFileSync(cacheIndex, JSON.stringify(cache), { encoding : 'utf8' });
        events.emit('done', data);
    }).on('stop', forward(events, 'stop'));
    return events;
}

exports.loadrepository = function(repoUrl, options) {
    options = utils.extend(options, { process : retire.replaceVersion });
    if (options.nocache) {
        return loadJson(repoUrl, options);
    }
    return loadFromCache(repoUrl, options.cachedir, options);
};

exports.loadrepositoryFromFile = function(filepath, options) {
...
```

#### <a name="apidoc.element.retire.utils.find"></a>[function <span class="apidocSignatureSpan">retire.utils.</span>find (ar, fn)](#apidoc.element.retire.utils.find)
- description and source-code
```javascript
find = function (ar, fn) {
	for(var i in ar) {
		if (fn(ar[i])) return ar[i];
	}
	return undefined;
}
```
- example usage
```shell
...
		listdep({component: pkginfo.name, version: pkginfo.version}, pkginfo, 1, deps);
		events.emit('done', deps);				
	});
	return events;
}

function scanJsFiles(path) {
	var finder = walkdir.find(path);
	finder.on('file', function (file) {
		if (file.match(/\.js$/)) {
			finder.emit('jsfile', file);
		}
		if (file.match(/\/bower.json$/)) {
			finder.emit('bowerfile', file);
		}
...
```

#### <a name="apidoc.element.retire.utils.flatten"></a>[function <span class="apidocSignatureSpan">retire.utils.</span>flatten (e)](#apidoc.element.retire.utils.flatten)
- description and source-code
```javascript
flatten = function (e) {
	return e.reduce(function(x,y) { return x.concat(y); }, []);
}
```
- example usage
```shell
...
  component.vulnerabilities.forEach(function(vulnerability){
    string += options.outputformat === 'clean' ? '\n   ' : ' ';
    if (vulnerability.severity) {
      string += 'severity: ' + vulnerability.severity + '; ';
    }
    if (vulnerability.identifiers) {
      string += utils.map(vulnerability.identifiers, function(id, name) {
        return name + ': ' + utils.flatten([id]).join(' ');
      }).join(', ') + '; ';
    }
    string += vulnerability.info.join(options.outputformat === 'clean' ? '\n' : ' ');
  });
  return string;
}
...
```

#### <a name="apidoc.element.retire.utils.forwardEvent"></a>[function <span class="apidocSignatureSpan">retire.utils.</span>forwardEvent (emitter, event)](#apidoc.element.retire.utils.forwardEvent)
- description and source-code
```javascript
forwardEvent = function (emitter, event) {
	return function() {
		emitter.emit([event].concat(arguments));
	};
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.retire.utils.log"></a>[function <span class="apidocSignatureSpan">retire.utils.</span>log (options)](#apidoc.element.retire.utils.log)
- description and source-code
```javascript
log = function (options) {
	return {
		info : info(options),
		warn : warn(options),
		verbose : options.verbose ? info(options) : function() {}
	};
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.retire.utils.map"></a>[function <span class="apidocSignatureSpan">retire.utils.</span>map (o, fn)](#apidoc.element.retire.utils.map)
- description and source-code
```javascript
map = function (o, fn) {
	return Object.keys(o).map(function(k) { return fn(o[k], k); });
}
```
- example usage
```shell
...
  var string = '';
  component.vulnerabilities.forEach(function(vulnerability){
    string += options.outputformat === 'clean' ? '\n   ' : ' ';
    if (vulnerability.severity) {
      string += 'severity: ' + vulnerability.severity + '; ';
    }
    if (vulnerability.identifiers) {
      string += utils.map(vulnerability.identifiers, function(id, name) {
        return name + ': ' + utils.flatten([id]).join(' ');
      }).join(', ') + '; ';
    }
    string += vulnerability.info.join(options.outputformat === 'clean' ? '\n' : ' ');
  });
  return string;
}
...
```

#### <a name="apidoc.element.retire.utils.pick"></a>[function <span class="apidocSignatureSpan">retire.utils.</span>pick (p, keys)](#apidoc.element.retire.utils.pick)
- description and source-code
```javascript
pick = function (p, keys) {
	var result = {};
	keys.forEach(function(k) {
		if (p.hasOwnProperty(k)) {
			result[k] = p[k];
		}
	});
	return result;
}
```
- example usage
```shell
...
			result[k] = p[k];
		}
	});
	return result;
};

exports.extend = function(o, a) {
	var result = exports.pick(o, Object.keys(o));
	exports.map(a, function(v,k){ result[k] = v; });
	return result;
};

exports.map = function(o, fn) {
	return Object.keys(o).map(function(k) { return fn(o[k], k); });
};
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
