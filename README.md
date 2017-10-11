# dynamic-clj
Provide dynamic versions of `import` and `require` 

Based on https://github.com/clojure/clojure/blob/master/src/jvm/clojure/lang/Reflector.java .
The idea is to be able to load classes, methods and namespaces with their name of the class/method in variables.
Something like `(import-dyn (class-name :as foo))` 
and static methods as `(foo / method-name 5 4 3)` 
or instance methods as `(let [x (foo . 5)] (x . method-name 4 3))` 
where class-name and method-name are strings [require-dyn would be similar]. 

The import could check that the supplied variable conform to an interface.
In that case it may be possible for the method calls to be more conventional.
