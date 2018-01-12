---
title: "Gliederung der Änderungen (C + c++ / CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c0bbbd6b-c5c4-44cf-a6ca-c1010c377e9d
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fdc0015bda5f0a6678b1d274c79445aba4e4aab0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="outline-of-changes-ccli"></a>Gliederung der Änderungen (C++/CLI)
Dieser Umriss zeigt Sie Beispiele für einige der Änderungen in der Sprache von Managed Extensions for C++ zu Visual C++. Führen Sie den Link, der jedes Element Informationen begleitet.  
  
## <a name="no-double-underscore-keywords"></a>Keine doppelten Unterstrich-Schlüsselwörter  
 Der doppelte Unterstrich vor alle Schlüsselwörter wurde entfernt, mit einer Ausnahme. Folglich `__value` wird `value`, und `__interface` wird `interface`und so weiter. Um Namenskonflikte zwischen Schlüsselwörtern und Bezeichnern im Benutzercode zu verhindern, werden Schlüsselwörter hauptsächlich kontextbezogen behandelt.  
  
 Finden Sie unter [Programmiersprachen-Schlüsselwörter (C + c++ / CLI)](../dotnet/language-keywords-cpp-cli.md) für Weitere Informationen.  
  
## <a name="class-declarations"></a>Klassendeklarationen  
 Verwaltete Extensions-Syntax:  
  
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
  
 Finden Sie unter [verwaltete Typen (C + c++ / CL)](../dotnet/managed-types-cpp-cl.md) für Weitere Informationen.  
  
## <a name="object-declaration"></a>Objektdeklaration  
 Verwaltete Extensions-Syntax:  
  
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
  
 Finden Sie unter [Deklaration eines CLR-Klasse Verweisobjekt](../dotnet/declaration-of-a-clr-reference-class-object.md) für Weitere Informationen.  
  
### <a name="managed-heap-allocation"></a>Verwaltete Heapreservierung  
 Verwaltete Extensions-Syntax:  
  
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
  
 Finden Sie unter [Deklaration eines CLR-Klasse Verweisobjekt](../dotnet/declaration-of-a-clr-reference-class-object.md) für Weitere Informationen.  
  
### <a name="a-tracking-reference-to-no-object"></a>Ein Nachverfolgungsverweis auf kein Objekt  
 Verwaltete Extensions-Syntax:  
  
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
  
 Finden Sie unter [Deklaration eines CLR-Klasse Verweisobjekt](../dotnet/declaration-of-a-clr-reference-class-object.md) für Weitere Informationen.  
  
## <a name="array-declaration"></a>Arraydeklaration  
 Die CLR-Array wurde überarbeitet. Es ist ähnlich der STL- `vector` Vorlagensammlung jedoch Zuordnungen auf den zugrunde liegenden `System::Array` class: d. h. es ist keine Vorlage Implementierung.  
  
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
  
### <a name="array-as-return-type"></a>Arrays als Rückgabetyp.  
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
  
### <a name="shorthand-initialization-of-local-clr-array"></a>Kurznotation für die Initialisierung des lokalen CLR-Array  
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
  
### <a name="explicit-clr-array-declaration"></a>Explizite CLR-Arraydeklaration  
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
  
 Neue Sprachelemente: explizite Arrayinitialisierung Gcnew der folgende  
  
```  
// explicit initialization list follow gcnew   
// is not supported in Managed Extensions  
array<Object^>^ myArray =   
   gcnew array<Object^>(4){ 1, 1, 2, 3 };  
```  
  
## <a name="scalar-properties"></a>Skalare Eigenschaften  
 Verwaltete Eigenschaft Extensions-Syntax:  
  
```  
public __gc __sealed class Vector {  
   double _x;  
  
public:  
   __property double get_x(){ return _x; }  
   __property void set_x( double newx ){ _x = newx; }  
};  
```  
  
 Neue Eigenschaftensyntax für die:  
  
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
  
 Neue Sprachelemente: triviale Eigenschaften  
  
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
 Managed Extensions indizierte Eigenschaftensyntax:  
  
```  
public __gc class Matrix {  
   float mat[,];  
  
public:   
   __property void set_Item( int r, int c, float value) { mat[r,c] = value; }  
   __property int get_Item( int r, int c ) { return mat[r,c]; }  
};  
```  
  
 Neue Syntax für die indizierte Eigenschaft:  
  
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
  
 Neue Sprachelemente: indizierte Eigenschaft auf Klassenebene  
  
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
  
 Neuer Operator Überladung Syntax:  
  
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
 Verwaltete Erweiterungen Konvertierungsoperatorsyntax:  
  
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
 Managed Extensions expliziten überschreiben Syntax:  
  
```  
public __gc class R : public ICloneable {  
   // to be used through ICloneable  
   Object* ICloneable::Clone();  
  
   // to be used through an R  
   R* Clone();  
};  
```  
  
 Neue Syntax für explizites Überschreiben:  
  
```  
public ref class R : public ICloneable {  
   // to be used through ICloneable  
   virtual Object^ InterfaceClone() = ICloneable::Clone;  
  
   // to be used through an R   
   virtual R^ Clone();  
};  
```  
  
 Finden Sie unter [explizites Überschreiben eines Schnittstellenmembers](../dotnet/explicit-override-of-an-interface-member.md) für Weitere Informationen.  
  
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
 Verwaltete Enumeration Extensions-Syntax:  
  
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
  
 Abgesehen von dieser kleinen syntaktischen Änderung wurde das Verhalten der CLR-Enumerationstyp auf vielfältige Weise geändert:  
  
-   Eine Vorwärtsdeklaration einer CLR-Enumeration wird nicht mehr unterstützt.  
  
-   Managed Extensions und Visual C++ verfügt über die Auflösung von funktionsüberladungen zwischen den integrierten arithmetischen Typen und die Klassenhierarchie für Objekt umgekehrt. Als Nebeneffekt werden die CLR-Enumerationen nicht mehr implizit in arithmetische Typen konvertiert.  
  
-   In der neuen Syntax verwaltet eine CLR-Enumeration einen eigenen Bereich, der nicht der Fall in Managed Extensions ist. Zuvor waren Enumeratoren innerhalb des enthaltenen Bereichs der Enumeration sichtbar; Enumeratoren werden jetzt innerhalb des Bereichs der Enumeration gekapselt.  
  
 Finden Sie unter [CLR-Enumerationstyp](../dotnet/clr-enum-type.md) für Weitere Informationen.  
  
## <a name="removal-of-box-keyword"></a>Entfernen des __box-Schlüsselwort  
 Managed Extensions boxing Syntax:  
  
```  
Object *o = __box( 1024 ); // explicit boxing  
```  
  
 Neue Boxingsyntax:  
  
```  
Object ^o = 1024; // implicit boxing  
```  
  
 Finden Sie unter [Tracking Handle für einen Wert mittels Boxing konvertiert](../dotnet/a-tracking-handle-to-a-boxed-value.md) für Weitere Informationen.  
  
## <a name="pinning-pointer"></a>Feste Zeiger  
 Managed Extensions-Syntax für feste Zeiger:  
  
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
 Verwaltete Erweiterungen "typeof"-Schlüsselwort Syntax:  
  
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
 [C + c++ / CLI Migration Primer](../dotnet/cpp-cli-migration-primer.md)   
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)


