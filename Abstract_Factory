//first type of motherboard
abstract class ATX {
  final String mbFactory;
  ATX(this.mbFactory);
  void create();
}

//second type of motherboard
abstract class mATX {
  final String mbFactory;
  mATX(this.mbFactory);
  void create();
}

//first type of motherboard create for Factory1
class Factory1ATX extends ATX {
  Factory1ATX() : super('Factory 1');

  @override
  void create() {
    print('Created ATX for $mbFactory');
  }
}

//second type of motherboard create for Factory1
class Factory1mATX extends mATX {
  Factory1mATX() : super('Factory 1');

  @override
  void create() {
    print('Created mATX for $mbFactory');
  }
}

//first type of motherboard create for Factory2
class Factory2ATX extends ATX {
  Factory2ATX() : super('Factory 2');

  @override
  void create() {
    print('Created ATX for $mbFactory');
  }
}

//second type of motherboard create for Factory2
class Factory2mATX extends mATX {
  Factory2mATX() : super('Factory 2');

  @override
  void create() {
    print('Created mATX for $mbFactory');
  }
}

//Base class of abstract factory
abstract class MBAbstractFactory {
  ATX getATX();
  mATX getmATX();
}

//realization abstract factory for Factory 1
class MBFactory1 implements MBAbstractFactory {
  @override
  ATX getATX() {
    return Factory1ATX();
  }

  @override
  mATX getmATX() {
    return Factory1mATX();
  }
}

//realization abstract factory for Factory 2
class MBFactory2 implements MBAbstractFactory {
  @override
  ATX getATX() {
    return Factory2ATX();
  }

  @override
  mATX getmATX() {
    return Factory2mATX();
  }
}

enum TypeFactory { MBFactory1, MBFactory2 }

class Factory {
  final MBAbstractFactory mbFactory;

  Factory(this.mbFactory);

  void createMB() {
    var atx = mbFactory.getATX()..create();
    var matx = mbFactory.getmATX()..create();
  }
}

class MBFactory {
  static MBAbstractFactory factory(TypeFactory typeFactory) {
    switch (typeFactory) {
      case TypeFactory.MBFactory1:
        return MBFactory1();
      case TypeFactory.MBFactory2:
        return MBFactory2();
      default:
        throw ArgumentError();
    }
  }
}

void main(List<String> arguments) {
  var typeFactory = TypeFactory.MBFactory2;
  var mbFactory = MBFactory.factory(typeFactory);
  var factory1 = Factory(mbFactory);
  factory1.createMB();
}
