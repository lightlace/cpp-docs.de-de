---
title: "Verwenden &quot;dllimport&quot; und &quot;dllexport&quot; in C++-Klassen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Klassen [C++], Deklarieren"
  - "Klassen [C++], Exportierbare und Vererbung"
  - "Deklarationen [C++], Klasse"
  - "Deklarieren von Klassen"
  - "dllexport-Attribut [C++]"
  - "dllexport-Attribut [C++], Klassen"
  - "dllimport-Attribut [C++], Klassen"
  - "Exportierbare Klassen [C++]"
  - "Exportieren von Klassen"
  - "Vererbung [C++], Exportierbare Klassen"
ms.assetid: 8d7d1303-b9e9-47ca-96cc-67bf444a08a9
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden &quot;dllimport&quot; und &quot;dllexport&quot; in C++-Klassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Sie können C\+\+\-Klassen mit dem **dllimport**\- oder dem `dllexport`\-Attribut deklarieren.  Hierbei ist impliziert, dass die gesamte Klasse importiert oder exportiert wird.  Klassen, die auf diese Weise exportiert werden, werden als exportierbare Klassen bezeichnet.  
  
 Im folgenden Beispiel wird eine exportierbare Klasse definiert.  All ihre Memberfunktionen und statischen Daten werden exportiert:  
  
```  
#define DllExport   __declspec( dllexport )  
  
class DllExport C {  
   int i;  
   virtual int func( void ) { return 1; }  
};  
```  
  
 Beachten Sie, dass die explizite Verwendung der **dllimport**\- und der `dllexport`\-Attribute für Member einer exportierbaren Klasse nicht zulässig ist.  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bdllexportclasses"></a> dllexport\-Klassen  
 Wenn Sie eine `dllexport`\-Klasse deklarieren, werden all ihre Memberfunktionen und statischen Datenmember exportiert.  Sie müssen die Definitionen all dieser Member im gleichen Programm bereitstellen.  Andernfalls wird ein Linkerfehler generiert.  Die einzige Ausnahme dieser Regel gilt für rein virtuelle Funktionen, für die keine expliziten Definitionen bereitgestellt werden müssen.  Da jedoch ein Destruktor für eine abstrakte Klasse immer vom Destruktor für die Basisklasse aufgerufen wird, müssen rein virtuelle Destruktoren immer eine Definition bereitstellen.  Beachten Sie, dass diese Regeln auch für nicht exportierbare Klassen gelten.  
  
 Wenn Sie Daten vom Klassentyp oder Funktionen, die Klassen zurückgeben, exportieren, stellen Sie sicher, dass Sie die Klasse exportieren.  
  
##  <a name="_pluslang_dllexport_classesdllexportclasses"></a> dllimport\-Klassen  
 Wenn Sie eine **dllimport**\-Klasse deklarieren, werden all ihre Memberfunktionen und statischen Datenmember importiert.  Im Gegensatz zum Verhalten von **dllimport** und `dllexport` für Nichtklassentypen können statische Datenmember keine Definition in dem gleichen Programm angeben, in dem eine **dllimport**\-Klasse definiert ist.  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2binheritanceandexportableclasses"></a> Vererbung und exportierbare Klassen  
 Alle Basisklassen einer exportierbaren Klasse müssen exportierbar sein.  Wenn dies nicht der Fall ist, wird eine Compilerwarnung ausgegeben.  Darüber hinaus müssen alle zugreifbaren Member, die auch Klassen sind, exportierbar sein.  Durch diese Regel ist es möglich, dass eine `dllexport`\-Klasse von einer **dllimport**\-Klasse erbt und eine **dllimport**\-Klasse von einer `dllexport`\-Klasse erbt \(auch wenn Letzteres nicht empfohlen wird.\)  In der Regel sollte alles, auf das der DLL\-Client zugreifen kann \(gemäß C\+\+\-Zugriffsregeln\), Teil der exportierbaren Schnittstelle sein.  Hierzu zählen die privaten Datenmember, auf die in Inlinefunktionen verwiesen wird.  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bselectivememberimportexport"></a> Selektiver Memberimport und \-export  
 Da Memberfunktionen und statische Daten innerhalb einer Klasse implizit externe Verknüpfungen aufweisen, können Sie sie mit dem **dllimport**\- oder dem `dllexport`\-Attribut deklarieren, es sei denn, die gesamte Klasse wird exportiert.  Wenn die gesamte Klasse importiert oder exportiert wird, ist die explizite Deklaration von Memberfunktionen und Daten als **dllimport** oder `dllexport` unzulässig.  Wenn Sie einen statischen Datenmember innerhalb einer Klassendefinition als `dllexport` deklarieren, muss eine Definition innerhalb desselben Programms auftreten \(wie bei externer Nichtklassenverknüpfung\).  
  
 Entsprechend können Sie Memberfunktionen mit dem **dllimport**\- oder dem `dllexport`\-Attribut deklarieren.  In diesem Fall müssen Sie eine `dllexport`\-Definition an einer beliebigen Stelle innerhalb desselben Programms bereitstellen.  
  
 Es wird empfohlen, einige wichtige Aspekte hinsichtlich des selektiven Memberimports und \-exports zu beachten:  
  
-   Der selektive Memberimport und \-export wird am besten zum Bereitstellen einer Version der exportierten Klassenschnittstelle verwendet, die restriktiver ist, also eine Schnittstelle, für die Sie eine DLL entwerfen können, die weniger öffentliche und private Funktionen verfügbar macht, als die Programmiersprache andernfalls zulassen würde.  Er ist auch zum Optimieren der exportierbaren Schnittstelle nützlich: Wenn Sie wissen, dass der Client definitionsgemäß nicht in der Lage ist, auf einige private Daten zuzugreifen, müssen Sie nicht die gesamte Klasse exportieren.  
  
-   Wenn Sie eine virtuelle Funktion in einer Klasse exportieren, müssen Sie alle exportieren, oder Sie müssen zumindest Versionen bereitstellen, die der Client direkt verwenden kann.  
  
-   Wenn Sie über eine Klasse verfügen, in der Sie selektiven Memberimport und \-export mit virtuellen Funktionen verwenden, müssen die Funktionen in der exportierbaren Schnittstelle auftreten oder inline definiert \(für den Client sichtbar\) sein.  
  
-   Wenn Sie einen Member als `dllexport` definieren, ihn jedoch nicht in der Klassendefinition einschließen, wird ein Compilerfehler generiert.  Sie müssen den Member im Header der Klasse definieren.  
  
-   Obwohl die Definition von Klassenmembern als **dllimport** oder `dllexport` zulässig ist, können Sie die Schnittstelle nicht überschreiben, die in der Klassendefinition angegeben wird.  
  
-   Wenn Sie eine Memberfunktion an einer anderen Stelle als im Text der Klassendefinition definieren, in der sie deklariert wurde, wird eine Warnung ausgegeben, wenn die Funktion als `dllexport` oder **dllimport** definiert wird \(wenn sich diese Definition von der unterscheidet, die in der Klassendeklaration angegeben wurde\).  
  
### END Microsoft\-spezifisch  
  
## Siehe auch  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)