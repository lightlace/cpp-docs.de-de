---
title: Verwenden von dllimport und dllexport in C++-Klassen
ms.date: 11/04/2016
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
ms.openlocfilehash: 3e8545f058043dfbb8abffc86cf987d0315ba3a7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660758"
---
# <a name="using-dllimport-and-dllexport-in-c-classes"></a>Verwenden von dllimport und dllexport in C++-Klassen

## <a name="microsoft-specific"></a>Microsoft-spezifisch

Sie können C++-Klassen mit deklarieren die **Dllimport** oder **Dllexport** Attribut. Hierbei ist impliziert, dass die gesamte Klasse importiert oder exportiert wird. Klassen, die auf diese Weise exportiert werden, werden als exportierbare Klassen bezeichnet.

Im folgenden Beispiel wird eine exportierbare Klasse definiert. All ihre Memberfunktionen und statischen Daten werden exportiert:

```cpp
#define DllExport   __declspec( dllexport )

class DllExport C {
   int i;
   virtual int func( void ) { return 1; }
};
```

Beachten Sie, dass explizite Verwendung des der **Dllimport** und **Dllexport** -Attribute für Member einer exportierbaren Klasse ist nicht zulässig.

##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bdllexportclasses"></a> Dllexport-Klassen

Wenn Sie eine Klasse deklarieren **Dllexport**, alle ihre Memberfunktionen und statischen Datenmember werden exportiert. Sie müssen die Definitionen all dieser Member im gleichen Programm bereitstellen. Andernfalls wird ein Linkerfehler generiert. Die einzige Ausnahme dieser Regel gilt für rein virtuelle Funktionen, für die keine expliziten Definitionen bereitgestellt werden müssen. Da jedoch ein Destruktor für eine abstrakte Klasse immer vom Destruktor für die Basisklasse aufgerufen wird, müssen rein virtuelle Destruktoren immer eine Definition bereitstellen. Beachten Sie, dass diese Regeln auch für nicht exportierbare Klassen gelten.

Wenn Sie Daten vom Klassentyp oder Funktionen, die Klassen zurückgeben, exportieren, stellen Sie sicher, dass Sie die Klasse exportieren.

##  <a name="_pluslang_dllexport_classesdllexportclasses"></a> DllImport-Klassen

Wenn Sie eine Klasse deklarieren **Dllimport**, alle ihre Memberfunktionen und statischen Datenmember importiert werden. Im Unterschied zum **Dllimport** und **Dllexport** für nichtklassentypen können statische Datenmember können nicht zum Angeben einer Definition in der gleichen Anwendung in dem eine **Dllimport** -Klasse ist definiert.

##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2binheritanceandexportableclasses"></a> Vererbung und exportierbare Klassen

Alle Basisklassen einer exportierbaren Klasse müssen exportierbar sein. Wenn dies nicht der Fall ist, wird eine Compilerwarnung ausgegeben. Darüber hinaus müssen alle zugreifbaren Member, die auch Klassen sind, exportierbar sein. Diese Regel erlaubt eine **Dllexport** Klasse geerbt eine **Dllimport** -Klasse, und ein **Dllimport** Klasse geerbt eine **Dllexport** die Klasse (auch wenn Letzteres nicht empfohlen wird). In der Regel sollte alles, auf das der DLL-Client zugreifen kann (gemäß C++-Zugriffsregeln), Teil der exportierbaren Schnittstelle sein. Hierzu zählen die privaten Datenmember, auf die in Inlinefunktionen verwiesen wird.

##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bselectivememberimportexport"></a> Selektiver Memberimport und-Export

Da Memberfunktionen und statische Daten innerhalb einer Klasse implizit externe Verknüpfungen aufweisen, können Sie sie deklarieren die **Dllimport** oder **Dllexport** Attribut, es sei denn, die gesamte Klasse exportiert wird. Wenn die gesamte Klasse importiert oder exportiert wird, die explizite Deklaration von Memberfunktionen und Daten als **Dllimport** oder **Dllexport** ist nicht zulässig. Wenn Sie einen statischen Datenmember innerhalb einer Klassendefinition als deklarieren **Dllexport**, eine Definition muss innerhalb desselben Programms (wie bei externer nichtklassenverknüpfung) an einer beliebigen Stelle erfolgen.

Auf ähnliche Weise können Sie deklarieren, Member-Funktionen mit den **Dllimport** oder **Dllexport** Attribute. In diesem Fall müssen Sie angeben einer **Dllexport** Definition an einer beliebigen Stelle innerhalb desselben Programms.

Es wird empfohlen, einige wichtige Aspekte hinsichtlich des selektiven Memberimports und -exports zu beachten:

- Der selektive Memberimport und -export wird am besten zum Bereitstellen einer Version der exportierten Klassenschnittstelle verwendet, die restriktiver ist, also eine Schnittstelle, für die Sie eine DLL entwerfen können, die weniger öffentliche und private Funktionen verfügbar macht, als die Programmiersprache andernfalls zulassen würde. Er ist auch zum Optimieren der exportierbaren Schnittstelle nützlich: Wenn Sie wissen, dass der Client definitionsgemäß nicht in der Lage ist, auf einige private Daten zuzugreifen, müssen Sie nicht die gesamte Klasse exportieren.

- Wenn Sie eine virtuelle Funktion in einer Klasse exportieren, müssen Sie alle exportieren, oder Sie müssen zumindest Versionen bereitstellen, die der Client direkt verwenden kann.

- Wenn Sie über eine Klasse verfügen, in der Sie selektiven Memberimport und -export mit virtuellen Funktionen verwenden, müssen die Funktionen in der exportierbaren Schnittstelle auftreten oder inline definiert (für den Client sichtbar) sein.

- Wenn Sie ein Element als definieren **Dllexport** , aber fügen Sie es nicht in der Klassendefinition, ein Compilerfehler generiert. Sie müssen den Member im Header der Klasse definieren.

- Obwohl die Definition von Klassenmembern als **Dllimport** oder **Dllexport** ist zulässig, können Sie die Schnittstelle, die in der Klassendefinition angegeben überschreiben.

- Wenn Sie eine Memberfunktion an einer Stelle als im Text der Klassendefinition definieren, in dem Sie wurde deklariert, wird eine Warnung generiert, wenn die Funktion, als definiert wurde **Dllexport** oder **Dllimport** (Wenn diese Definition unterscheidet, die in der Klassendeklaration angegeben).

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[dllexport, dllimport](../cpp/dllexport-dllimport.md)