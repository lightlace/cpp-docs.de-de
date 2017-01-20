---
title: "Gliederung der &#196;nderungen (C++/CLI)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: c0bbbd6b-c5c4-44cf-a6ca-c1010c377e9d
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# Gliederung der &#196;nderungen (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgende Gliederung soll als Kurzreferenz der Sprachänderungen in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] gegenüber Managed Extensions for C\+\+ dienen.  Folgen Sie den jeweiligen Links, um weitere Informationen zu erhalten.  
  
## Keine Schlüsselwörter mit doppeltem Unterstrich  
 Der allen Schlüsselwörtern vorangestellte doppelte Unterstrich wurde entfernt – mit einer Ausnahme.  Somit wird `__value` zu `value` und `__interface` zu `interface` usw.  Um Namenskonflikte zwischen Schlüsselwörtern und Bezeichnern im Benutzercode zu verhindern, werden Schlüsselwörter hauptsächlich kontextbezogen behandelt.  
  
 Weitere Informationen finden Sie unter [Sprachschlüsselwörter \(C\+\+\/CLI\)](../dotnet/language-keywords-cpp-cli.md).  
  
## Klassendeklarationen  
 Managed Extensions\-Syntax:  
  
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
  
 Weitere Informationen finden Sie unter [Verwaltete Typen \(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md).  
  
## Objektdeklaration  
 Managed Extensions\-Syntax:  
  
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
  
 Weitere Informationen finden Sie unter [Deklaration eines CLR\-Verweisklassenobjekts](../dotnet/declaration-of-a-clr-reference-class-object.md).  
  
### Reservierung auf dem verwalteten Heap  
 Managed Extensions\-Syntax:  
  
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
  
 Weitere Informationen finden Sie unter [Deklaration eines CLR\-Verweisklassenobjekts](../dotnet/declaration-of-a-clr-reference-class-object.md).  
  
### Ein Nachverfolgungsverweis auf kein Objekt  
 Managed Extensions\-Syntax:  
  
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
  
 Weitere Informationen finden Sie unter [Deklaration eines CLR\-Verweisklassenobjekts](../dotnet/declaration-of-a-clr-reference-class-object.md).  
  
## Arraydeklaration  
 Das CLR\-Array ist umgestaltet worden.  Es ähnelt der stl\-`vector`\-Vorlagenauflistung, ist jedoch der zugrunde liegenden `System::Array`\-Klasse zugeordnet, d. h. es handelt sich nicht um eine Vorlagenimplementierung.  
  
 Weitere Informationen finden Sie unter [Deklaration eines CLR\-Arrays](../dotnet/declaration-of-a-clr-array.md).  
  
### Arrays als Parameter  
 Managed Extensions\-Arraysyntax:  
  
```  
void PrintValues( Object* myArr __gc[]);   
void PrintValues( int myArr __gc[,,]);   
```  
  
 Neue Arraysyntax:  
  
```  
void PrintValues( array<Object^>^ myArr );  
void PrintValues( array<int,3>^ myArr );  
```  
  
### Arrays als Rückgabetyp  
 Managed Extensions\-Arraysyntax:  
  
```  
Int32 f() [];   
int GetArray() __gc[];  
```  
  
 Neue Arraysyntax:  
  
```  
array<Int32>^ f();  
array<int>^ GetArray();  
```  
  
### Kurznotation für die Initialisierung lokaler CLR\-Arrays  
 Managed Extensions\-Arraysyntax:  
  
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
  
### Explizite CLR\-Arraydeklaration  
 Managed Extensions\-Arraysyntax:  
  
```  
Object* myArray[] = new Object*[2];  
String* myMat[,] = new String*[4,4];  
```  
  
 Neue Arraysyntax:  
  
```  
array<Object^>^ myArray = gcnew array<Object^>(2);  
array<String^,2>^ myMat = gcnew array<String^,2>(4,4);  
```  
  
 Neue Sprachelemente: explizite, auf gcnew folgende Arrayinitialisierung  
  
```  
// explicit initialization list follow gcnew   
// is not supported in Managed Extensions  
array<Object^>^ myArray =   
   gcnew array<Object^>(4){ 1, 1, 2, 3 };  
```  
  
## Skalare Eigenschaften  
 Managed Extensions\-Eigenschaftensyntax:  
  
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
   } // Note: no semi-colon …  
};  
```  
  
 Neue Sprachelemente: Triviale Eigenschaften  
  
```  
public ref class Vector sealed {   
public:  
   // equivalent shorthand property syntax  
   // backing store is not accessible  
   property double x;   
};  
```  
  
 Weitere Informationen finden Sie unter [Eigenschaftendeklaration](../dotnet/property-declaration.md).  
  
## Indizierte Eigenschaften  
 Indizierte Eigenschaftensyntax in Managed Extensions:  
  
```  
public __gc class Matrix {  
   float mat[,];  
  
public:   
   __property void set_Item( int r, int c, float value) { mat[r,c] = value; }  
   __property int get_Item( int r, int c ) { return mat[r,c]; }  
};  
```  
  
 Neue indizierte Eigenschaftensyntax:  
  
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
  
 Neue Sprachelemente: Indizierte Eigenschaften auf Klassenebene  
  
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
  
 Weitere Informationen finden Sie unter [Deklaration von Eigenschaftenindizes](../dotnet/property-index-declaration.md).  
  
## Überladene Operatoren  
 Managed Extensions\-Operatorüberladungssyntax:  
  
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
  
 Neue Operatorüberladungssyntax:  
  
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
  
 Weitere Informationen finden Sie unter [Überladene Operatoren](../dotnet/overloaded-operators.md).  
  
## Konvertierungsoperatoren  
 Managed Extensions\-Konvertierungsoperatorsyntax:  
  
```  
__gc struct MyDouble {  
   static MyDouble* op_Implicit( int i );   
   static int op_Explicit( MyDouble* val );  
   static String* op_Explicit( MyDouble* val );   
};  
```  
  
 Neue Konvertierungsoperatorsyntax:  
  
```  
ref struct MyDouble {  
public:  
   static operator MyDouble^ ( int i );  
   static explicit operator int ( MyDouble^ val );  
   static explicit operator String^ ( MyDouble^ val );  
};  
```  
  
 Weitere Informationen finden Sie unter [Änderungen bei Konvertierungsoperatoren](../dotnet/changes-to-conversion-operators.md).  
  
## Explizites Überschreiben eines Schnittstellenmembers  
 Syntax für explizites Überschreiben in Managed Extensions:  
  
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
  
 Weitere Informationen finden Sie unter [Explizites Überschreiben eines Schnittstellenmembers](../dotnet/explicit-override-of-an-interface-member.md).  
  
## Private virtuelle Funktionen  
 Syntax für private virtuelle Funktionen in Managed Extensions:  
  
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
  
 Weitere Informationen finden Sie unter [Private virtuelle Funktionen](../dotnet/private-virtual-functions.md).  
  
## CLR\-Enumerationstyp  
 Managed Extensions\-Enumerationssyntax:  
  
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
  
 Abgesehen von dieser kleinen syntaktischen Änderung hat sich eine Reihe von Änderungen beim Verhalten des CLR\-Enumerationstyps ergeben:  
  
-   Die Vorwärtsdeklaration einer CLR\-Enumeration wird nicht mehr unterstützt.  
  
-   Die Überladungsauflösung zwischen den integrierten arithmetischen Typen und der Objektklassenhierarchie wurde in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] gegenüber Managed Extensions umgekehrt.  Als Nebeneffekt werden CLR\-Enumerationen nicht mehr implizit in arithmetische Typen konvertiert.  
  
-   In der neuen Syntax verwaltet eine CLR\-Enumeration ihren eigenen Gültigkeitsbereich, was bei Managed Extensions nicht der Fall ist.  Vorher waren die Enumeratoren im enthaltenen Gültigkeitsbereich der Enumeration sichtbar; jetzt sind die Enumeratoren im Gültigkeitsbereich der Enumeration gekapselt.  
  
 Weitere Informationen finden Sie unter [CLR\-Enumerationstyp](../dotnet/clr-enum-type.md).  
  
## Entfernen des \_\_box\-Schlüsselworts  
 Managed Extensions\-Boxingsyntax:  
  
```  
Object *o = __box( 1024 ); // explicit boxing  
```  
  
 Neue Boxingsyntax:  
  
```  
Object ^o = 1024; // implicit boxing  
```  
  
 Weitere Informationen finden Sie unter [Ein Trackinghandle für einen geschachtelten Wert](../dotnet/a-tracking-handle-to-a-boxed-value.md).  
  
## Feste Zeiger  
 Syntax für feste Zeiger in Managed Extensions:  
  
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
  
 Weitere Informationen finden Sie unter [Werttypsemantik](../dotnet/value-type-semantics.md).  
  
## \_\_typeof\-Schlüsselwort wird zu typeid  
 Managed Extensions\-typeof\-Syntax:  
  
```  
Array* myIntArray =   
   Array::CreateInstance( __typeof(Int32), 5 );  
```  
  
 Neue typeid\-Syntax:  
  
```  
Array^ myIntArray =   
   Array::CreateInstance( Int32::typeid, 5 );  
```  
  
 Weitere Informationen finden Sie unter [typeof wird zu T::typeid](../dotnet/typeof-goes-to-t-typeid.md).  
  
## Siehe auch  
 [Einführung in die C\+\+\/CLI\-Migration](../dotnet/cpp-cli-migration-primer.md)   
 [\(NOTINBUILD\)Managed Extensions for C\+\+ Syntax Upgrade Checklist](assetId:///edbded88-7ef3-4757-bd9d-b8f48ac2aada)   
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)