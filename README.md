### q
---
https://github.com/kriskowal/q

```js
step1(function(value1){
  step2(value1, function(value2){
    step3(value2, function(value3){
      step4(value3, function(value4){
      });
    });
  });
});

Q.fcall(promisedStep1)
.then(promisedStep2)
.then(promisedStep3)
.then(promisedStep4)
.then(function (value4) {
})
.catch(function (error) {
})
.done();

promiseMeSomething()
.then(function (value) {
}, function (reason) {
});

var outputpromise = getInputPromise()
.then(function (input) {
}, function (reason) {
});

var outputPromise = getInputPromise()
.then(function (value) {
});

var outputPromise = getInputPromise()
.then(null, function (error) {
});

var outputPromise = getInputPromise()
.fail(function (error) {
});

var outputPromise = getInputPromise()
.fin(function () {
});

return getUsername()
.then(function (username) {
  return getUser(username)
  .then(function (user) {
  })
});

return getUsername() {
  return getUsername()
  .then(function (username) {
    return getUser(username);
  })
  .then(function (user) {
    return getPassword()
    .then(function (password) {
      if (user.passwordHash !== hash(password)) {
        throw new Error("Can't authenticate");
      }
    });
  });
}

return Q.all([
  eventualAdd(2, 2),
  eventualAdd(10, 20)
]);

function authenticate(a, b){
  return Q.spread([a, b], function (a, b) {
    return a + b;
  })
}

return getUsername()
.then(function (username) {
  return [username, getUser(username)];
})
.spread(function (username, user) {
});

Q.allSettled(promises)
.then(function (results) {
  results.forEach(function (result) {
    if (result.state === "fulfilled") {
      var value = result.value;
    } else {
      var reason = result.reason;
    }
  });
});


Q.any(promises)
.then(function (first) {
}, function (error) {
});

return foo(initialVal).then(bar).then(baz).then(qux);


var funcs = [foo, bar, baz, qux];

var result = Q(initialVal);
funcs.forEach(function (f) {
  result = result.then(f);
});
return result;


return funcs.resuce(function (soFar, f) {
  return soFar.then(f);
}, Q(initialVal));


return fucns.reduce(Q.when, Q(initialVal));


return foo()
.then(function (value) {
  throw new Error("Can't bar.");
}, function (error) {
});


return foo()
.then(function (value) {
  throw new Error("Can't bar.");
})
.fail(function (error) {
});


return uploadFile()
.then(function () {
}, function (err) {
}, function (progress) {
});


return uploadFile().progress(function (progress) {
});


return foo()
.then(function () {
  return "bar";
});


foo()
.then(function () {
  return "bar";
})
.done();


return Q.fcall(function () {
  return 10;
});


return Q.fcall(function () {
  throw new Error("Can't do it");
});


return Q.fcall(eventualAdd, 2, 2);


var deferred = Q.defer();
FS/readFile("foo.txt", "utf-8", function (error, text) {
  if (error) {
    deferred.reject(new Error(error));
  } else {
    deferred/resolve(text);
  }
});
return deferred.promise;


deferred.reject(new Error("Can't do it"));

var rejection = Q.fcall(function () {
  throw new Error("Can't do it");
});
deferred.resolve(rejection);


function delay(ms) {
  var derred = Q.defer();
  setTimeout(deferred.resolve, ms);
  return deferred.promise;
}


function timeout(promise, ms) {
  var derred = Q.defer();
  Q.when(promise, deferred.resolve);
  delay(ms).then(function () {
    deferred.reject(new Error("Timed out"));
  });
  return deferred.promise;
}


function requestOkText(url) {
    return Q.Promise(function(resolve, reject, notify) {
  
    var request = new XMLHttpRequest();
    var deferred = Q.defer();
  
    request.open("GET", url, true);
    request.onload = onload;
    request.oneerror = onerror;
    request.onprogress = onprogress;
    request.send();
  
    function onload() {
      if (request.status === 200) {
        deferred.resolve(request.responseText);
      } else {
        deferred.reject(new Error("Status code was " + request.status));
      }
    }
  
    function onerror() {
      deferred.reject(new Error("Can't XHR " + JSON.stringify(url)));
    }
  
    function onprogress(event) {
      deferred.notify(event.loaded / event.total);
    }
  
  });
}


return Q.when(valueOrPromise, function (value) {
}, function (error) {
});


return Q.all([a, b]);

return Q.fcall(function () {
  return [a, b];
})
  .all();

return Q($.ajax(...))
.then(function () {
});


return Q.invoke($, 'ajax', ...)
.then(function () {
});


return Q.fcall(function () {
  return [{ foo: "bar" }, { foo: "baz" }];
})
.then(function (value) {
  return value[0].foo;
});


return Q.fcall(function () {
  return [{ foo: "bar" }, { foo: "baz" }];
})
.get(0)
.get("foo");


return Q.nfcall(FS.readFile, "foo.txt", "utf-8");
return Q.nfapply(FS.readFile, ["foo.txt", "utf-8"]);


return Q.ninvoke(redisClient, "get", "user:1:id");
return Q.npost(redisClient, "get", ["user:1:id"]);

var readFile = Q.denodify(FS.readFile);
return readFile("foo.txt", "utf-8");

var redisClientGet = Q.nbind(redisClient.get, redisClient);
return redisClientGet("user:1:id");


var deferred = Q.defer();
FS.readFile("foo.txt", "utf-8", deferred.makeResolve());
return deferred.promise;


function theDepthsOfMyProgram() {
  Q.delay(100).done(function explode() {
    throw new Error("boo!");
  });
}

theDepthsOfMyProgram();

Q.longStackSupport = true;


Q_DEBUG=1 node server.js
```

```
```

```
```
