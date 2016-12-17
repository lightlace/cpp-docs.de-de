---
title: "functional (STL/CLR)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "<cliext/functional>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/functional>-Header [STL/CLR]"
  - "<functional>-Header [STL/CLR]"
  - "Funktionale Funktionen [STL/CLR]"
ms.assetid: 88738b8c-5d37-4375-970e-a4442bf5efde
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "mblome"
manager: "ghogen"
---
# functional (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Schließen Sie die STL\/CLR\-Header `<cliext/functional>` ein, um die einige Vorlagenklassen und die zugehörigen Vorlagendelegaten und Funktionen definieren.  
  
## Syntax  
  
```  
#include <functional>  
```  
  
## Deklarationen  
  
|Delegate|**Beschreibung**|  
|--------------|----------------------|  
|[binary\_delegate](../dotnet/binary-delegate-stl-clr.md)|Zwei\-Argumentdelegat.|  
|[binary\_delegate\_noreturn](../dotnet/binary-delegate-noreturn-stl-clr.md)|Zwei\-Argumentdelegat, der `void` zurückgibt.|  
|[unary\_delegate](../dotnet/unary-delegate-stl-clr.md)|Ein\-Argumentdelegat.|  
|[unary\_delegate\_noreturn](../dotnet/unary-delegate-noreturn-stl-clr.md)|Ein\-Argumentdelegat, der `void` zurückgibt.|  
  
|Klasse|**Beschreibung**|  
|------------|----------------------|  
|[binary\_negate](../dotnet/binary-negate-stl-clr.md)|Funktionselement, um ein ZweiArgumentfunktionselements zurückzusetzen.|  
|[binder1st](../dotnet/binder1st-stl-clr.md)|Funktionselement, z des ersten Arguments an einen ZweiArgumentfunktionselement zu binden.|  
|[binder2nd](../dotnet/binder2nd-stl-clr.md)|Funktionselement, z des zweiten Arguments an einen ZweiArgumentfunktionselement zu binden.|  
|[divides](../dotnet/divides-stl-clr.md)|Verteilungsfunktionselement.|  
|[equal\_to](../dotnet/equal-to-stl-clr.md)|Gleiches Vergleichsfunktionselement.|  
|[greater](../dotnet/greater-stl-clr.md)|Größeres Vergleichsfunktionselement.|  
|[greater\_equal](../dotnet/greater-equal-stl-clr.md)|Größeres oder gleich Vergleichsfunktionselement.|  
|[less](../dotnet/less-stl-clr.md)|Weniger Vergleichsfunktionselement.|  
|[less\_equal](../dotnet/less-equal-stl-clr.md)|Kleiner oder gleich Vergleichsfunktionselement.|  
|[logical\_and](../dotnet/logical-and-stl-clr.md)|Funktionselement des logischen AND\-Vorgangs.|  
|[logical\_not](../dotnet/logical-not-stl-clr.md)|Funktionselement des logischen Nicht.|  
|[logical\_or](../dotnet/logical-or-stl-clr.md)|Logisches Oder\-Funktionselement.|  
|[minus](../dotnet/minus-stl-clr.md)|Subtrahieren Funktionselement.|  
|[Modulo](../dotnet/modulus-stl-clr.md)|Modulo\-Funktionselement.|  
|[multiplies](../dotnet/multiplies-stl-clr.md)|Multiplizieren Funktionselement.|  
|[negate](../dotnet/negate-stl-clr.md)|Funktionselement, deren Arguments zurückzugeben negiert.|  
|[not\_equal\_to](../dotnet/not-equal-to-stl-clr.md)|Nicht Vergleichsfunktionselement entspricht.|  
|[plus](../dotnet/plus-stl-clr.md)|Fügen Sie Funktionselement hinzu.|  
|[unary\_negate](../dotnet/unary-negate-stl-clr.md)|Funktionselement, um ein EinArgumentfunktionselements zurückzusetzen.|  
  
|Funktion|**Beschreibung**|  
|--------------|----------------------|  
|[bind1st](../dotnet/bind1st-stl-clr.md)|Generiert ein binder1st für ein Argument und ein Funktionselement.|  
|[bind2nd](../dotnet/bind2nd-stl-clr.md)|Generiert ein binder2nd für ein Argument und ein Funktionselement.|  
|[not1](../dotnet/not1-stl-clr.md)|Generiert ein unary\_negate für ein Funktionselement.|  
|[not1](../dotnet/not1-stl-clr.md)|Generiert ein binary\_negate für ein Funktionselement.|  
  
## Anforderungen  
 **Header:** \<cliext\/funktionsfähig\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [STL\/CLR\-Bibliothek](../dotnet/stl-clr-library-reference.md)