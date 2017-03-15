---
title: "Eigenschaftendeklaration | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__property-Schlüsselwort"
  - "Deklarieren von Eigenschaften, C++"
  - "property-Schlüsselwort [C++]"
ms.assetid: de169378-a8b8-49f4-a586-76bffc9b5c9f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Eigenschaftendeklaration
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Art und Weise, eine Eigenschaft in einer verwalteten Klasse zu deklarieren, hat sich in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] gegenüber Managed Extensions for C\+\+ geändert.  
  
 Im Managed Extensions\-Design wird jeder `set`\-Eigenschaftenaccessor oder `get`\-Eigenschaftenaccessor als unabhängige Methode angegeben.  Jeder Methodendeklaration wird das `__property`\-Schlüsselwort vorangestellt.  Der Methodenname beginnt entweder mit `set_` oder `get_`, gefolgt vom Namen der Eigenschaft \(wie für den Benutzer sichtbar\).  Demnach würde der Methodenname für einen `Vector`, der eine `x`\-Koordinate als `get`\-Eigenschaft bereitstellt, `get_x` lauten, und der Benutzer würde die Eigenschaft als `x` aufrufen.  Diese Namenskonvention und separate Spezifikation von Methoden spiegelt die zugrunde liegende Laufzeitimplementierung der Eigenschaft wider.  Nehmen wir als Beispiel den zuvor erwähnten `Vector` mit einer Reihe von Koordinateneigenschaften:  
  
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
  
 Bei dieser Syntax ist die einer Eigenschaft zugeordnete Funktionalität verteilt, und der Benutzer muss die zugeordneten sets und gets lexikalisch zusammenführen.  Außerdem ist sie umständlich.  In der neuen Syntax, die der Syntax von C\# ähnelt, folgt nach dem `property`\-Schlüsselwort der Typ der Eigenschaft und ihr einfacher Name.  Die `set`\-Zugriffsmethode und die `get`\-Zugriffsmethode werden in einen Block unterhalb des Eigenschaftennamens eingefügt  Beachten Sie, dass im Unterschied zu C\# die Signatur der Zugriffsmethode angegeben wird.  Es folgt das obige Codebeispiel in der neuen Syntax.  
  
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
  
 Wenn die Zugriffsmethoden der Eigenschaft bestimmte Zugriffsebenen widerspiegeln, z. B. `get` die Zugriffsebene `public` und `set` die Zugriffsebene `private` oder `protected`, kann eine explizite Zugriffsbezeichnung angegeben werden.  Standardmäßig spiegelt die Zugriffsebene der Eigenschaft die einschließende Zugriffsebene wider.  So wurden z. B. in der obigen Definition von `Vector` sowohl die `get`\-Methode als auch die `set`\-Methode als `public` festgelegt.  Um die `set`\-Methode als `protected` oder `private` festzulegen, müsste die Definition folgendermaßen überarbeitet werden:  
  
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
  
   } // note: extent of private culminates here …  
  
// note: dot is a public method of Vector  
double dot( const Vector^ wv );  
  
// etc.  
};  
```  
  
 Der Gültigkeitsbereich eines Zugriffsschlüsselworts innerhalb einer Eigenschaft reicht entweder bis zur schließenden Klammer der Eigenschaft oder bis zur Spezifikation eines weiteren Zugriffsschlüsselworts.  Er überschreitet nicht die Definition der Eigenschaft in der einschließenden Zugriffsebene, in der die Eigenschaft definiert ist.  In der oben erwähnten Deklaration handelt es sich beispielsweise bei `Vector::dot()` um eine öffentliche Methode.  
  
 Das Schreiben der set\/get\-Eigenschaften für die drei `Vector`\-Koordinaten umfasst drei Schritte:  
  
1.  Deklarieren eines privaten Zustandsmembers vom entsprechenden Typ  
  
2.  Zurückgeben des Members, wenn der Benutzer dessen Wert abrufen möchte  
  
3.  Festlegen des Members auf den neuen Wert  
  
 In der neuen Syntax steht eine Kurznotation für die Eigenschaftensyntax zur Verfügung, die dieses Verwendungsmuster automatisiert:  
  
```  
public ref class Vector sealed {   
public:  
   // equivalent shorthand property syntax  
   property double x;   
   property double y;  
   property double z;  
};  
```  
  
 Ein interessanter Nebeneffekt der Kurznotation für die Eigenschaftensyntax liegt darin, dass der Hintergrundzustandsmember zwar vom Compiler generiert wird, er aber innerhalb der Klasse trotzdem nur mithilfe der set\/get\-Accessoren verfügbar ist.  
  
## Siehe auch  
 [Memberdeklarationen innerhalb einer Klasse oder Schnittstelle \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [property](../windows/property-cpp-component-extensions.md)