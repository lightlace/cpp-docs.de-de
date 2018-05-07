---
title: Eigenschaftendeklaration | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __property keyword
- declaring properties, C++
- property keyword [C++]
ms.assetid: de169378-a8b8-49f4-a586-76bffc9b5c9f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bc2cf76384078e579756abe653fb45fd1e97707f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="property-declaration"></a>Eigenschaftendeklaration
Die Möglichkeit zum Deklarieren einer Eigenschaft in einer verwalteten Klasse wurde von Managed Extensions für C++ in Visual C++ geändert.  
  
 In Managed Extensions entwerfen, jede `set` oder `get` Eigenschaftenaccessor als unabhängige Methode angegeben ist. Die Deklaration der einzelnen Methoden vorangestellt ist die `__property` Schlüsselwort. Der Name der Methode beginnt entweder mit `set_` oder `get_` gefolgt von den tatsächlichen Namen der Eigenschaft (wie für den Benutzer sichtbar). Folglich eine `Vector` Bereitstellen einer `x` koordinieren `get` Eigenschaft nennen sie `get_x` und der Benutzer würde rufen Sie sie als `x`. Diese Benennungskonvention und die Methoden eine separate Spezifikation tatsächlich wiedergibt die zugrunde liegenden Common Language Runtime-Implementierung der Eigenschaft. Hier ist z. B. unsere `Vector` mit einem Satz von Koordinaten Eigenschaften:  
  
```  
public __gc __sealed class Vector {  
public:  
   __property double get_x(){ return _x; }  
   __property double get_y(){ return _y; }  
   __property double get_z(){ return _z; }  
  
   __property void set_x( double newx ){ _x = newx; }  
   __property void set_y( double newy ){ _y = newy; }  
   __property void set_z( double newz ){ _z = newz; }  
};  
```  
  
 Die Funktionen in Zusammenhang mit der Eigenschaft ausbreitet, und erfordert, dass der Benutzer die zugeordneten Sets und ruft lexikalisch vereinheitlichen. Darüber hinaus ist es ausführlich. In der neuen Syntax von c# ähnelt, die `property` Schlüsselwort folgt den Typ der Eigenschaft und ihr einfacher Name. Die `set` und `get` -Zugriffsmethode werden innerhalb eines Blocks nach dem Eigenschaftennamen. Beachten Sie, dass anders als bei c#, die Signatur der Zugriffsmethode angegeben ist. Hier ist z. B. im Codebeispiel oben in der neuen Syntax übersetzt wird.  
  
```  
public ref class Vector sealed {   
public:  
   property double x {  
      double get() {  
         return _x;  
      }  
  
      void set( double newx ) {  
         _x = newx;  
      }  
   } // Note: no semi-colon  
};  
```  
  
 Die Zugriffsmethoden der Eigenschaft unterschiedliche Zugriffsebenen - wieder, wie z. B. eine `public get` und ein `private` oder `protected set`, eine Bezeichnung explicit Zugriff kann angegeben werden. Standardmäßig gibt die Zugriffsebene der Eigenschaft, die für die einschließende Zugriffsebene wieder. Beispielsweise ist in der obigen Definition von `Vector`, die beide die `get` und `set` Methoden sind `public`. Vornehmen der `set` Methode `protected` oder `private`, die Definition würde wie folgt überarbeitet werden:  
  
```  
public ref class Vector sealed {   
public:  
   property double x {  
      double get() {  
         return _x;  
      }  
  
   private:  
      void set( double newx ) {  
         _x = newx;  
      }  
  
   } // note: extent of private culminates here  
  
// note: dot is a public method of Vector  
double dot( const Vector^ wv );  
  
// etc.  
};  
```  
  
 Der Gültigkeitsbereich eines Zugriffsschlüsselworts auf innerhalb einer Eigenschaft erstreckt sich bis zu der schließenden Klammer der Eigenschaft oder die Spezifikation eines Zugriffsschlüsselworts auf zusätzliche. Es ist nicht länger als die Definition der Eigenschaft, die die einschließende Zugriffsebene sein, anhand derer die Eigenschaft definiert ist. In der oben genannten Deklaration, z. B. `Vector::dot()` ist eine öffentliche Methode.  
  
 Das Schreiben der Set/Get-Eigenschaften für die drei `Vector` Koordinaten umfasst drei Schritte:  
  
1.  Deklarieren Sie einen privaten Status-Member des entsprechenden Typs.  
  
2.  Geben sie zurück, wenn der Benutzer den Wert abrufen möchte.  
  
3.  Weisen sie den neuen Wert.  
  
 In der neuen Syntax steht eine Kurzsyntax für die Eigenschaft der dieses Nutzungsmuster automatisiert:  
  
```  
public ref class Vector sealed {   
public:  
   // equivalent shorthand property syntax  
   property double x;   
   property double y;  
   property double z;  
};  
```  
  
 Interessante Nebeneffekt von der Eigenschaft Kurzsyntax besteht darin, dass obwohl das backstage-Status-Element vom Compiler generiert wird, nicht innerhalb der Klasse mit Ausnahme der Set/Get-Accessoren zugegriffen werden kann.  
  
## <a name="see-also"></a>Siehe auch  
 [Memberdeklarationen innerhalb einer Klasse oder Schnittstelle (C + c++ / CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [Eigenschaft](../windows/property-cpp-component-extensions.md)