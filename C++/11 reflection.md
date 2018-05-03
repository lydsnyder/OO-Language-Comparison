# Reflection

### What reflection abilities are supported?
C++ does not natively support reflection mechanism.
### How is reflection used?
However, not so long ago RTTI support was added to the language but it only provides restricted subset of reflection: it allows to get object compile-time and runtime type (it is possible to get object runtime type if object class contains virtual functions). You can compare types and you can get type name - and that is all you can do with RTTI.
