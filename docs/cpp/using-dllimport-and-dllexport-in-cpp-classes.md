---
title: Verwenden von Dllimport und Dllexport in C++-Klassen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- exporting classes [C++]
- declarations [C++], class
- exportable classes [C++]
- classes [C++], declaring
- classes [C++], exportable and inheritance
- inheritance [C++], exportable classes [C++]
- dllimport attribute [C++], classes
- declaring classes [C++]
- dllexport attribute [C++]
- dllexport attribute [C++], classes [C++]
ms.assetid: 8d7d1303-b9e9-47ca-96cc-67bf444a08a9
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 6085672be99f6ddeb6d5b124eaf62f34e67e45f9
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="using-dllimport-and-dllexport-in-c-classes"></a>Verwenden von dllimport und dllexport in C++-Klassen
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Sie können mit Visual C++-Klassen deklarieren die **Dllimport** oder `dllexport` Attribut. Hierbei ist impliziert, dass die gesamte Klasse importiert oder exportiert wird. Klassen, die auf diese Weise exportiert werden, werden als exportierbare Klassen bezeichnet.  
  
 Im folgenden Beispiel wird eine exportierbare Klasse definiert. All ihre Memberfunktionen und statischen Daten werden exportiert:  
  
```  
#define DllExport   __declspec( dllexport )  
  
class DllExport C {  
   int i;  
   virtual int func( void ) { return 1; }  
};  
```  
  
 Beachten Sie, dass explizite Verwendung des der **Dllimport** und `dllexport` -Attribute für Member einer exportierbaren Klasse ist nicht zulässig.  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bdllexportclasses"></a>Dllexport-Klassen  
 Wenn Sie eine `dllexport`-Klasse deklarieren, werden all ihre Memberfunktionen und statischen Datenmember exportiert. Sie müssen die Definitionen all dieser Member im gleichen Programm bereitstellen. Andernfalls wird ein Linkerfehler generiert. Die einzige Ausnahme dieser Regel gilt für rein virtuelle Funktionen, für die keine expliziten Definitionen bereitgestellt werden müssen. Da jedoch ein Destruktor für eine abstrakte Klasse immer vom Destruktor für die Basisklasse aufgerufen wird, müssen rein virtuelle Destruktoren immer eine Definition bereitstellen. Beachten Sie, dass diese Regeln auch für nicht exportierbare Klassen gelten.  
  
 Wenn Sie Daten vom Klassentyp oder Funktionen, die Klassen zurückgeben, exportieren, stellen Sie sicher, dass Sie die Klasse exportieren.  
  
##  <a name="_pluslang_dllexport_classesdllexportclasses"></a>DllImport-Klassen  
 Wenn Sie eine Klasse deklarieren **Dllimport**, ihre Memberfunktionen und statischen Datenmember importiert werden. Im Gegensatz zu das Verhalten des **Dllimport** und `dllexport` für nichtklassentypen können statische Datenmember können nicht zum Angeben einer Definition im selben Programm in der eine **Dllimport** Klasse definiert ist.  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2binheritanceandexportableclasses"></a>Vererbung und exportierbare Klassen  
 Alle Basisklassen einer exportierbaren Klasse müssen exportierbar sein. Wenn dies nicht der Fall ist, wird eine Compilerwarnung ausgegeben. Darüber hinaus müssen alle zugreifbaren Member, die auch Klassen sind, exportierbar sein. Diese Regel erlaubt eine `dllexport` Klasse zu vererben eine **Dllimport** -Klasse, und ein **Dllimport** Klasse zu vererben eine `dllexport` Klasse (obwohl Letzteres nicht empfohlen). In der Regel sollte alles, auf das der DLL-Client zugreifen kann (gemäß C++-Zugriffsregeln), Teil der exportierbaren Schnittstelle sein. Hierzu zählen die privaten Datenmember, auf die in Inlinefunktionen verwiesen wird.  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bselectivememberimportexport"></a>Selektiver Memberimport und-Export  
 Da Memberfunktionen und statische Daten innerhalb einer Klasse implizit externe Verknüpfungen aufweisen, können Sie deklarieren sie mit der **Dllimport** oder `dllexport` Attribut, es sei denn, die gesamte Klasse exportiert wird. Wenn die gesamte Klasse importiert oder exportiert, die explizite Deklaration von Memberfunktionen und Daten als **Dllimport** oder `dllexport` ist nicht zulässig. Wenn Sie einen statischen Datenmember innerhalb einer Klassendefinition als `dllexport` deklarieren, muss eine Definition innerhalb desselben Programms auftreten (wie bei externer Nichtklassenverknüpfung).  
  
 Auf ähnliche Weise können Sie deklarieren Elements Funktionen mit dem **Dllimport** oder `dllexport` Attribute. In diesem Fall müssen Sie eine `dllexport`-Definition an einer beliebigen Stelle innerhalb desselben Programms bereitstellen.  
  
 Es wird empfohlen, einige wichtige Aspekte hinsichtlich des selektiven Memberimports und -exports zu beachten:  
  
-   Der selektive Memberimport und -export wird am besten zum Bereitstellen einer Version der exportierten Klassenschnittstelle verwendet, die restriktiver ist, also eine Schnittstelle, für die Sie eine DLL entwerfen können, die weniger öffentliche und private Funktionen verfügbar macht, als die Programmiersprache andernfalls zulassen würde. Er ist auch zum Optimieren der exportierbaren Schnittstelle nützlich: Wenn Sie wissen, dass der Client definitionsgemäß nicht in der Lage ist, auf einige private Daten zuzugreifen, müssen Sie nicht die gesamte Klasse exportieren.  
  
-   Wenn Sie eine virtuelle Funktion in einer Klasse exportieren, müssen Sie alle exportieren, oder Sie müssen zumindest Versionen bereitstellen, die der Client direkt verwenden kann.  
  
-   Wenn Sie über eine Klasse verfügen, in der Sie selektiven Memberimport und -export mit virtuellen Funktionen verwenden, müssen die Funktionen in der exportierbaren Schnittstelle auftreten oder inline definiert (für den Client sichtbar) sein.  
  
-   Wenn Sie einen Member als `dllexport` definieren, ihn jedoch nicht in der Klassendefinition einschließen, wird ein Compilerfehler generiert. Sie müssen den Member im Header der Klasse definieren.  
  
-   Obwohl die Definition von Klassenmembern als **Dllimport** oder `dllexport` ist zulässig, können Sie die Schnittstelle, die in der Klassendefinition angegeben überschreiben.  
  
-   Wenn Sie eine Memberfunktion an einer anderen Stelle als im Text der Klassendefinition definieren, in dem Sie wurde deklariert, wird eine Warnung generiert, wenn die Funktion, als definiert ist `dllexport` oder **Dllimport** (sofern diese Definition von unterscheidet. in der Klassendeklaration angegeben).  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)
