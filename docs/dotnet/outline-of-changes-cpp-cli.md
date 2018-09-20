---
title: Gliederung der Änderungen (C++ / CLI) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c0bbbd6b-c5c4-44cf-a6ca-c1010c377e9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cfdf502d5529232b856f85a031ff90392d7c2ff0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415121"
---
# <a name="outline-of-changes-ccli"></a>Gliederung der Änderungen (C++/CLI)

Dieser Umriss zeigt Beispiele für einige der Änderungen in der Sprache von Managed Extensions für C++, Visual c++. Führen Sie den Link, der einzelnen Elemente, um weitere Informationen zu begleitet.

## <a name="no-double-underscore-keywords"></a>Keine doppelten Unterstrich-Schlüsselwörter

Der doppelte Unterstrich vor alle Schlüsselwörter wurde mit einer Ausnahme entfernt wurde. Daher `__value` wird `value`, und `__interface` wird `interface`und so weiter. Um Namenskonflikte zwischen Schlüsselwörtern und Bezeichnern im Benutzercode zu verhindern, werden in erster Linie Schlüsselwörter kontextbezogen behandelt.

Finden Sie unter [Sprachschlüsselwörter (C++ / CLI)](../dotnet/language-keywords-cpp-cli.md) für Weitere Informationen.

## <a name="class-declarations"></a>Klassendeklarationen

Syntax für verwaltete Erweiterungen:

```
__gc class Block {};                           // reference class
__value class Vector {};                       // value class
__interface I {};                        // interface class
__gc __abstract class Shape {};                // abstract class
__gc __sealed class Shape2D : public Shape {}; // derived class
```

Neue Syntax:

```
ref class Block {};                // reference class
value class Vector {};             // value class
interface class I {};        // interface class
ref class Shape abstract {};       // abstract class
ref class Shape2D sealed: Shape{}; // derived class
```

Finden Sie unter [verwaltete Typen (C++ / CL)](../dotnet/managed-types-cpp-cl.md) für Weitere Informationen.

## <a name="object-declaration"></a>Objektdeklaration

Syntax für verwaltete Erweiterungen:

```
public __gc class Form1 : public System::Windows::Forms::Form {
private:
   System::ComponentModel::Container __gc *components;
   System::Windows::Forms::Button   __gc *button1;
   System::Windows::Forms::DataGrid __gc *myDataGrid;
   System::Data::DataSet  __gc *myDataSet;
};
```

Neue Syntax:

```
public ref class Form1 : System::Windows::Forms::Form {
   System::ComponentModel::Container^ components;
   System::Windows::Forms::Button^ button1;
   System::Windows::Forms::DataGrid^ myDataGrid;
   System::Data::DataSet^ myDataSet;
};
```

Finden Sie unter [Deklaration eines CLR-Verweisklassenobjekts](../dotnet/declaration-of-a-clr-reference-class-object.md) für Weitere Informationen.

### <a name="managed-heap-allocation"></a>Verwaltete Heapreservierung

Syntax für verwaltete Erweiterungen:

```
Button* button1 = new Button; // managed heap
int *pi1 = new int;           // native heap
Int32 *pi2 = new Int32;       // managed heap
```

Neue Syntax:

```
Button^ button1 = gcnew Button;        // managed heap
int * pi1 = new int;                   // native heap
Int32^ pi2 = gcnew Int32;              // managed heap
```

Finden Sie unter [Deklaration eines CLR-Verweisklassenobjekts](../dotnet/declaration-of-a-clr-reference-class-object.md) für Weitere Informationen.

### <a name="a-tracking-reference-to-no-object"></a>Ein Nachverfolgungsverweis auf kein Objekt

Syntax für verwaltete Erweiterungen:

```
// OK: we set obj to refer to no object
Object * obj = 0;

// Error: no implicit boxing
Object * obj2 = 1;
```

Neue Syntax:

```
// Incorrect Translation
// causes the implicit boxing of both 0 and 1
Object ^ obj = 0;
Object ^ obj2 = 1;

// Correct Translation
// OK: we set obj to refer to no object
Object ^ obj = nullptr;

// OK: we initialize obj2 to an Int32^
Object ^ obj2 = 1;
```

Finden Sie unter [Deklaration eines CLR-Verweisklassenobjekts](../dotnet/declaration-of-a-clr-reference-class-object.md) für Weitere Informationen.

## <a name="array-declaration"></a>Arraydeklaration

Das CLR-Array wurde neu gestaltet. Es ist ähnlich der STL- `vector` Vorlagensammlung, aber die Zuordnungen auf den zugrunde liegenden `System::Array` class: d. h. es ist keine vorlagenimplementierung.

Finden Sie unter [Deklaration eines CLR-Arrays](../dotnet/declaration-of-a-clr-array.md) für Weitere Informationen.

### <a name="array-as-parameter"></a>Arrays als Parameter

Verwaltete Erweiterungen Array-Syntax:

```
void PrintValues( Object* myArr __gc[]);
void PrintValues( int myArr __gc[,,]);
```

Neue Arraysyntax:

```
void PrintValues( array<Object^>^ myArr );
void PrintValues( array<int,3>^ myArr );
```

### <a name="array-as-return-type"></a>Array als Rückgabetyp.

Verwaltete Erweiterungen Array-Syntax:

```
Int32 f() [];
int GetArray() __gc[];
```

Neue Arraysyntax:

```
array<Int32>^ f();
array<int>^ GetArray();
```

### <a name="shorthand-initialization-of-local-clr-array"></a>Kurznotation für die Initialisierung von lokalen CLR-Arrays

Verwaltete Erweiterungen Array-Syntax:

```
int GetArray() __gc[] {
   int a1 __gc[] = { 1, 2, 3, 4, 5 };
   Object* myObjArray __gc[] = { __box(26), __box(27), __box(28),
                                 __box(29), __box(30) };

   return a1;
}
```

Neue Arraysyntax:

```
array<int>^ GetArray() {
   array<int>^ a1 = {1,2,3,4,5};
   array<Object^>^ myObjArray = {26,27,28,29,30};

   return a1;
}
```

### <a name="explicit-clr-array-declaration"></a>Explizite CLR-Array-Deklaration

Verwaltete Erweiterungen Array-Syntax:

```
Object* myArray[] = new Object*[2];
String* myMat[,] = new String*[4,4];
```

Neue Arraysyntax:

```
array<Object^>^ myArray = gcnew array<Object^>(2);
array<String^,2>^ myMat = gcnew array<String^,2>(4,4);
```

Neue Sprache: explizite Arrayinitialisierung, die Gcnew folgt

```
// explicit initialization list follow gcnew
// is not supported in Managed Extensions
array<Object^>^ myArray =
   gcnew array<Object^>(4){ 1, 1, 2, 3 };
```

## <a name="scalar-properties"></a>Skalare Eigenschaften

Verwaltete Erweiterungen Eigenschaft-Syntax:

```
public __gc __sealed class Vector {
   double _x;

public:
   __property double get_x(){ return _x; }
   __property void set_x( double newx ){ _x = newx; }
};
```

Neue Eigenschaftensyntax:

```
public ref class Vector sealed {
   double _x;

public:
   property double x
   {
      double get()             { return _x; }
      void   set( double newx ){ _x = newx; }
   } // Note: no semi-colon
};
```

Neue Sprache: triviale Eigenschaften

```
public ref class Vector sealed {
public:
   // equivalent shorthand property syntax
   // backing store is not accessible
   property double x;
};
```

Finden Sie unter [Eigenschaftendeklaration](../dotnet/property-declaration.md) für Weitere Informationen.

## <a name="indexed-properties"></a>Indizierte Eigenschaften

Verwaltete Erweiterungen indizierte Eigenschaftensyntax:

```
public __gc class Matrix {
   float mat[,];

public:
   __property void set_Item( int r, int c, float value) { mat[r,c] = value; }
   __property int get_Item( int r, int c ) { return mat[r,c]; }
};
```

Syntax für neue indizierte Eigenschaft:

```
public ref class Matrix {
   array<float, 2>^ mat;

public:
   property float Item [int,int] {
      float get( int r, int c ) { return mat[r,c]; }
      void set( int r, int c, float value ) { mat[r,c] = value; }
   }
};
```

Neue Sprache: indizierte Eigenschaft auf Klassenebene

```
public ref class Matrix {
   array<float, 2>^ mat;

public:
   // ok: class level indexer now
   //     Matrix mat;
   //     mat[ 0, 0 ] = 1;
   //
   // invokes the set accessor of the default indexer

   property float default [int,int] {
      float get( int r, int c ) { return mat[r,c]; }
      void set( int r, int c, float value ) { mat[r,c] = value; }
   }
};
```

Finden Sie unter [Eigenschaftenindizes](../dotnet/property-index-declaration.md) für Weitere Informationen.

## <a name="overloaded-operators"></a>Überladene Operatoren

Verwaltete Erweiterungen Überladung Operatorsyntax:

```
public __gc __sealed class Vector {
public:
   Vector( double x, double y, double z );

   static bool    op_Equality( const Vector*, const Vector* );
   static Vector* op_Division( const Vector*, double );
};

int main() {
   Vector *pa = new Vector( 0.231, 2.4745, 0.023 );
   Vector *pb = new Vector( 1.475, 4.8916, -1.23 );

   Vector *pc = Vector::op_Division( pa, 4.8916 );

   if ( Vector::op_Equality( pa, pc ))
      ;
}
```

Neue Syntax für die Operator-Überladung:

```
public ref class Vector sealed {
public:
   Vector( double x, double y, double z );

   static bool    operator ==( const Vector^, const Vector^ );
   static Vector^ operator /( const Vector^, double );
};

int main() {
   Vector^ pa = gcnew Vector( 0.231, 2.4745, 0.023 );
   Vector^ pb = gcnew Vector( 1.475, 4.8916, -1.23 );

   Vector^ pc = pa / 4.8916;
   if ( pc == pa )
      ;
}
```

Finden Sie unter [überladene Operatoren](../dotnet/overloaded-operators.md) für Weitere Informationen.

## <a name="conversion-operators"></a>Konvertierungsoperatoren

Verwaltete Erweiterungen Operator Konvertierungssyntax:

```
__gc struct MyDouble {
   static MyDouble* op_Implicit( int i );
   static int op_Explicit( MyDouble* val );
   static String* op_Explicit( MyDouble* val );
};
```

Neue Syntax für die Konvertierung-Operator:

```
ref struct MyDouble {
public:
   static operator MyDouble^ ( int i );
   static explicit operator int ( MyDouble^ val );
   static explicit operator String^ ( MyDouble^ val );
};
```

Finden Sie unter [Änderungen bei Konvertierungsoperatoren](../dotnet/changes-to-conversion-operators.md) für Weitere Informationen.

## <a name="explicit-override-of-an-interface-member"></a>Explizites Überschreiben eines Schnittstellenmembers

Verwaltete Erweiterungen, die explizit außer Kraft setzen Syntax aus:

```
public __gc class R : public ICloneable {
   // to be used through ICloneable
   Object* ICloneable::Clone();

   // to be used through an R
   R* Clone();
};
```

Neue explizite Überschreibungssyntax:

```
public ref class R : public ICloneable {
   // to be used through ICloneable
   virtual Object^ InterfaceClone() = ICloneable::Clone;

   // to be used through an R
   virtual R^ Clone();
};
```

Finden Sie unter [expliziten Überschreiben eines Schnittstellenmembers](../dotnet/explicit-override-of-an-interface-member.md) für Weitere Informationen.

## <a name="private-virtual-functions"></a>Private virtuelle Funktionen

Verwaltete private virtuelle Funktionen Extensions-Syntax:

```
__gc class Base {
private:
   // inaccessible to a derived class
   virtual void g();
};

__gc class Derived : public Base {
public:
   // ok: g() overrides Base::g()
   virtual void g();
};
```

Neue Syntax für private virtuelle Funktionen

```
ref class Base {
private:
   // inaccessible to a derived class
   virtual void g();
};

ref class Derived : public Base {
public:
   // error: cannot override: Base::g() is inaccessible
   virtual void g() override;
};
```

Finden Sie unter [Private virtuelle Funktionen](../dotnet/private-virtual-functions.md) für Weitere Informationen.

## <a name="clr-enum-type"></a>CLR-Enumerationstyp

Verwaltete Erweiterungen Enum-Syntax:

```
__value enum e1 { fail, pass };
public __value enum e2 : unsigned short  {
   not_ok = 1024,
   maybe, ok = 2048
};
```

Neue Enumerationssyntax:

```
enum class e1 { fail, pass };
public enum class e2 : unsigned short {
   not_ok = 1024,
   maybe, ok = 2048
};
```

Abgesehen von dieser kleinen Änderung syntaktische wurde das Verhalten von der CLR-Enumerationstyp auf verschiedene Arten geändert:

- Eine Vorwärtsdeklaration einer CLR-Enumeration wird nicht mehr unterstützt.

- Die Auflösung von funktionsüberladungen zwischen den integrierten arithmetischen Typen und die Hierarchie des Objekt-Klasse verfügt über Managed Extensions und Visual C++ rückgängig gemacht. Als Nebeneffekt werden die CLR-Enumerationen nicht mehr implizit in arithmetischen Typen konvertiert.

- In der neuen Syntax verwaltet eine CLR-Enumeration einen eigenen Bereich, der nicht in Managed Extensions der Fall ist. Zuvor waren Enumeratoren innerhalb des enthaltenen Bereichs der Enumeration sichtbar; Enumeratoren werden jetzt innerhalb des Bereichs der Enumeration gekapselt.

Finden Sie unter [CLR-Enumerationstyp](../dotnet/clr-enum-type.md) für Weitere Informationen.

## <a name="removal-of-box-keyword"></a>Entfernen von __box-Schlüsselwort

Verwaltete Erweiterungen boxing Syntax:

```
Object *o = __box( 1024 ); // explicit boxing
```

Neue Boxingsyntax:

```
Object ^o = 1024; // implicit boxing
```

Finden Sie unter [ein Handle nachverfolgen, auf einen Wert mittels Boxing konvertiert](../dotnet/a-tracking-handle-to-a-boxed-value.md) für Weitere Informationen.

## <a name="pinning-pointer"></a>Feste Zeiger

Verwaltete Erweiterungen, die Syntax für feste Zeiger:

```
__gc struct H { int j; };

int main() {
   H * h = new H;
   int __pin * k = & h -> j;
};
```

Neue Syntax für feste Zeiger:

```
ref struct H { int j; };

int main() {
   H^ h = gcnew H;
   pin_ptr<int> k = &h->j;
}
```

Finden Sie unter [Werttypsemantik](../dotnet/value-type-semantics.md) für Weitere Informationen.

## <a name="typeof-keyword-becomes-typeid"></a>__typeof-Schlüsselwort wird typeid

Verwaltete Erweiterungen Typeof-Syntax:

```
Array* myIntArray =
   Array::CreateInstance( __typeof(Int32), 5 );
```

Neue Typeid-Syntax:

```
Array^ myIntArray =
   Array::CreateInstance( Int32::typeid, 5 );
```

Finden Sie unter [Typeof wird zu t:: typeid](../dotnet/typeof-goes-to-t-typeid.md) für Weitere Informationen.

## <a name="see-also"></a>Siehe auch

[Einführung in die C++/CLI-Migration](../dotnet/cpp-cli-migration-primer.md)<br/>
[Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)

