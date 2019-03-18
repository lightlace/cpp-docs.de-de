---
title: Operatoren für den Präprozessorlauf eines Makefiles
ms.date: 06/14/2018
helpviewer_keywords:
- operators [C++], makefile preprocessing
- EXIST operator
- preprocessing NMAKE makefile operators
- NMAKE program, operators
- DEFINED operator
- makefiles, preprocessing operators
ms.assetid: a46e4d39-afdb-43c1-ac3b-025d33e6ebdb
ms.openlocfilehash: 4101c2fe30bcba44e9b69ed4d6d022845e6e8904
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57825581"
---
# <a name="makefile-preprocessing-operators"></a>Operatoren für den Präprozessorlauf eines Makefiles

Makefile-Vorverarbeitungsausdrücke können Operatoren verwenden, die auf konstante Werte, Exitcodes von Befehlen, Zeichenfolgen, Makros und Dateisystempfade angewendet werden. Zum Auswerten des Ausdrucks erweitert der Präprozessor zuerst Makros, führt dann Befehle aus und führt anschließend die Vorgänge durch. Vorgänge werden in der Reihenfolge der expliziten Gruppierung in Klammern ausgewertet und dann in der Reihenfolge der Operatorrangfolge. Das Ergebnis ist ein konstanter Wert.

Die **definierte** Operator ist ein logischer Operator, der auf einen Makronamen angewendet. Der Ausdruck **definiert (**_Macroname_**)** ist True, wenn *Macroname* definiert ist, auch wenn er nicht über einen zugewiesenen Wert verfügt. **Der benutzerdefinierte** in Kombination mit **! IF** oder **! ELSE IF** entspricht **! IFDEF** oder **! ANDERE IFDEF**. Anders als bei diesen Anweisungen kann **definierte** in komplexen Ausdrücken verwendet werden können.

Die **EXIST** Operator ist ein logischer Operator, der auf einen Dateisystempfad angewendet. **EXIST (**_Pfad_**)** ist True, wenn *Pfad* vorhanden ist. Das Ergebnis von **EXIST** kann in binären Ausdrücken verwendet werden. Wenn *Pfad* enthält Leerzeichen, müssen Sie ihn in doppelte Anführungszeichen ein.

Verwenden Sie den Gleichheitsoperator zum Vergleichen von zwei Zeichenfolgen (**==**) oder den Ungleichheitsoperator (**! =**) Operator. Schließen Sie Zeichenfolgen in doppelte Anführungszeichen ein.

Ganzzahlige Konstanten können die Unäroperatoren für numerische Negation (**-**) jeweils das Einerkomplement (**~**), und die logische Negation (**!**).

Ausdrücke können die folgenden Operatoren verwenden. Die Operatoren mit gleichem Rang werden zusammengruppiert, und die Gruppen werden absteigender Rangfolge aufgelistet. Unäre Operatoren werden dem Operanden rechts zugeordnet. Binäre Operatoren mit gleichem Rang werden den Operanden von links nach rechts zugeordnet.

|Operator|Beschreibung|
|--------------|-----------------|
|**Der benutzerdefinierte (** *Macroname* **)**|Produziert einen logischen Wert für den aktuellen definitionszustand von *Macroname*.|
|**EXIST (** *Pfad* **)**|Produziert einen logischen Wert für das Vorhandensein einer Datei an *Pfad*.|
|||
|**\!**|Unäres logisches NOT.|
|**~**|Unäres Einerkomplement.|
|**-**|Unäre Negation.|
|||
|**&#42;**|Multiplikation.|
|**/**|Division.|
|**%**|Modul (Rest).|
|||
|**+**|Addition.|
|**-**|Subtraktion.|
|||
|**\<\<**|Bitweise Verschiebung links.|
|**>>**|Bitweise Verschiebung rechts.|
|||
|**\<=**|Kleiner oder gleich.|
|**>=**|Größer oder gleich.|
|**\<**|Kleiner als.|
|**>**|Größer als.|
|||
|**==**|Gleichheit.|
|**\!=**|Ungleichheit.|
|||
|**&**|Bitweises AND.|
|**^**|Bitweises XOR.|
|**&#124;**|Bitweises OR.|
|||
|**&&**|Logisches AND.|
|||
|**&#124;&#124;**|Logisches OR.|

> [!NOTE]
> Der bitweise XOR-Operator (**^**) ist identisch mit dem Escapezeichen und muss mit Escapezeichen versehen werden (als **^^**) Wenn sie in einem Ausdruck verwendet wird.

## <a name="see-also"></a>Siehe auch

- [Ausdrücke für die Vorverarbeitung eines Makefiles](expressions-in-makefile-preprocessing.md)