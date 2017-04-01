# Tutorail
 - [Guice](https://github.com/google/guice)
    - User's Guide
         - [Motivation](https://github.com/google/guice/wiki/Motivation)
         - Link from a type to any of its subtypes, such as an implementing class or an extending class. You can even link the concrete DatabaseTransactionLog class to a subclass
            - ```bind(DatabaseTransactionLog.class).to(MySqlDatabaseTransactionLog.class);```
         - Linked bindings can also be chained
         - bindings support an optional binding annotation. The annotation and type together uniquely identify a binding. This pair is called a key.
            - Since the compiler can't check the string, we recommend using @Named sparingly. Defining your own purpose-built annotations provides better type-safety.
         - You can bind a type to a specific instance of that type. This is usually only useful only for objects that don't have dependencies of their own, such as value objects
            - Avoid using .toInstance with objects that are complicated to create, since it can slow down application startup. You can use an @Provides method instead.
         - When you need code to create an object, use an @Provides method.
         - Use @ImplementedBy carefully; it adds a compile-time dependency from the interface to its implementation.
         - Singletons are most useful for:
            - stateful objects, such as configuration or counters
            - objects that are expensive to construct or lookup
            - objects that tie up resources, such as a database connection pool.
         - To use optional injection, apply the @Inject(optional=true) annotation
         - Method and field injection can be used to initialize an existing instance. You can use the Injector.injectMembers API
         - Static members will not be injected at instance-injection time. This API is not recommended for general use because it suffers many of the same problems as static factories: it's clumsy to test, it makes dependencies opaque, and it relies on global state.
    - Best Practices
 
 
 
 
 
 
 
 
 
 
# Comparison
 - [Spring vs. Guice: The Clash of the IOC Containers](http://www.theserverside.com/feature/Spring-vs-Guice-The-Clash-of-the-IOC-Containers)
    - Although Spring provides many benefits, it was created in a pre-Java-5 world. The Guice framework takes DI to the next level, leveraging the full power of Java typing, especially annotations and generics.
    - Spring was one of the first DI frameworks available, and it offered a lighter-weight alternative to the heavy-handed approach of J2EE.
    - 1. Living in XML Hell
        - JavaConfig
    - 2. Eliminating reliance on String identifiers
        - Guice does support a type of String identifier via the @Named annotation, but its use is discouraged for the same reason. 
    - 3. Preferring Constructor Injection
        - Spring has long favored setter injection. 
        - Constructor injection, on the other hand, makes the creation of immutable classes easy, an important consideration in writing multi-threaded applications. 
    - 4. Nullifying NullPointerExceptions
        - By default, Guice refuses to inject a null into any object, and if an accidental null shows up during wiring, it fails-fast with a ProvisionException.
    - 5. Intruding into the domain
        - If the thought of having @Inject sprinkled through your codebase is still unbearable, Guice Provider methods are an alternative very similar to Spring JavaConfig to inject instances without using any Guice-specific annotations.
    - 6. Replacing Spring verbosity with Guicey compactness
        - configuration complexity when reusing dependencies.
    - 7. Considering other advantages
        - Guice fully supports generics, and has introduced mechanisms such as TypeLiterals and Provider methods to circumvent type erasure.
        - Wiring classes by type and disallowing the injection of nulls gives Guice a distinct advantage at run-time
        - an even more impressive feat considering that by default Guice injects a new and separate instance of an object for each dependency
 - [Comparing Spring vs. Google Guice: By Example](http://www.theserverside.com/feature/Comparing-Spring-vs-Google-Guice-By-Example)
    - Type Safety
    - static <-> runtime
    - you're annotating the class to be autowired, rather than the relationship between the class and its injection point.  
        - the compiler has no way to know if a class annotated with @Better actually matches the parameter annotated with @Better. 
    - The framework also starts from a fresh slate, without the need to rely on the concept of a bean or maintain backward compatibility with XML.
    - Spring wires classes together by bean, whereas Guice wires classes together by type.

# In Amazon
 - [GuiceAndDependencyInjection](https://w.888.com/index.php/GuiceAndDependencyInjection)
    - This makes testing much easier, because you can simply pass in a lightweight test/mock version of any dependency.
    - When should I use constructor injection vs. field injection (@Inject) vs Singleton.getInjector( )/Singleton.getMyClass( ) ?
        - When possible, we encourage using constructor injection. It has many advantages including but not limited to:
            - It is very easy to test classes that use constructor injection
            - Constructors implicitly convey the dependencies that the class has
            - Doesn't depend on Guice - good for testing
        - If constructor injection is not feasible, another option is to annotate the field you want to inject with @Inject
        - The third option is to use the Singletons class.
    - What are some other cool things I can do with Guice/RoboGuice?
        - Inject Android-y Things
        - Inject Views, Resources, Extras, And More!
        - @AnnotatedWith
        - @ContextScoped
    - How can I inject dependencies for integrated tests?
        - https://code.888.com/packages/GuiceJunitTestRunner/trees/GuiceJunitTestRunner-1.1
 - [Google Guice](https://w.888.com/bin/view/PeopleExperience/SDECurriculum/Guice/)
    -  Amazon has recently (2016) moved towards having Guice as the default framework for new projects.
        - https://code.888.com/packages/GuiceJunitTestRunner/trees/GuiceJunitTestRunner-1.1