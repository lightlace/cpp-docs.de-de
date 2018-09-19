---
title: Partial (Komponentenerweiterungen für C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- partial_CPP
dev_langs:
- C++
helpviewer_keywords:
- partial
- C++/CX, partial
ms.assetid: 43adf1f5-10c5-44aa-a66f-7507e2bdabf8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 92fd30b0b420080d33f9938bec4891ac80ac660d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42597077"
---
# <a name="partial--c-component-extensions"></a>Partial (Komponentenerweiterungen für C++)

Die **teilweise** mit dem Schlüsselwort können Sie verschiedene Teile der gleichen Verweisklasse unabhängig voneinander und in anderen Dateien erstellt werden.

## <a name="all-runtimes"></a>Alle Laufzeiten

(Diese Sprachfunktion gilt nur für die Windows-Runtime.)

## <a name="windows-runtime"></a>Windows-Runtime

Für einen Ref-Klasse, die beiden partielle Definitionen, verfügt die **teilweise** Schlüsselwort wird angewendet, auf das erste Vorkommen der Definition, und dies erfolgt normalerweise durch automatisch generierte Code, sodass menschlichen Programmierer das Schlüsselwort nicht sehr häufig verwendet. Lassen Sie für alle nachfolgenden partiellen Definitionen der Klasse, die **teilweise** Modifizierer aus der *Klassenschlüssel* -Schlüsselwort und Klasse-ID. Wenn der Compiler erkennt, eine zuvor definierte Verweisklasse und Klassen-ID, aber keine **teilweise** -Schlüsselwort, intern kombiniert alle Teile der Definition der Ref-Klasse in eine Definition.

### <a name="syntax"></a>Syntax

```cpp
partial class-key identifier {
   /* The first part of the partial class definition. 
      This is typically auto-generated */
}
// ...
class-key identifier {
   /* The subsequent part(s) of the class definition. The same 
      identifier is specified, but the "partial" keyword is omitted. */
}
```

### <a name="parameters"></a>Parameter

*Klassenschlüssel*  
Ein Schlüsselwort, das deklariert eine Klasse oder Struktur, die von der Windows-Runtime unterstützt wird. Entweder **Verweisklasse**, **Wertklasse**, **Referenzstruktur**, oder **wertstruktur**.

*identifier*  
Der Name des definierten Typs.

### <a name="remarks"></a>Hinweise

Eine partielle Klasse unterstützt Szenarien, in dem Sie einen Teil der Definition einer Klasse in eine Datei, und die Software für den automatischen Generieren von Code ändern, z. B. die XAML-Designer – ändert der Code in der gleichen Klasse in einer anderen Datei. Verwenden Sie eine partielle Klasse, können Sie verhindern, dass automatische Code-Generators Ihren Code überschreibt. In einem Visual Studio-Projekt die **teilweise** Modifizierer automatisch auf die generierte Datei angewendet wird.

Inhalt: Mit zwei Ausnahmen eine partielle Klassendefinition kann alles enthalten, die die vollständige Klassendefinition enthalten könnte, wenn die **teilweise** -Schlüsselwort ausgelassen wurde. Sie können nicht jedoch den Klassen-Barrierefreiheit angeben (z. B. `public partial class X { ... };`), oder ein **"declspec"**.

Zugriff auf Spezifizierer verwendet, die in einer partiellen Klassendefinition für *Bezeichner* wirken sich nicht auf die Standard-Barrierefreiheit in einer nachfolgenden partiellen oder vollständigen Klassendefinition für *Bezeichner*. Inlinedefinitionen statischer Datenmember sind zulässig.

Deklaration: Eine partielle Definition einer Klasse *Bezeichner* führt nur den Namen *Bezeichner*, aber *Bezeichner* kann nicht verwendet werden, auf eine Weise, die eine Klasse erforderlich sind. die Definition. Der Name *Bezeichner* kann nicht verwendet werden, um die Größe des wissen *Bezeichner*, oder verwenden eine Basis oder ein Mitglied *Bezeichner* bis nach der der Compiler die vollständige Definition der trifft *Bezeichner*.

Anzahl und Reihenfolge: Es darf null oder mehr partielle Klassendefinitionen für *Bezeichner*. Jede partielle Klassendefinition von *Bezeichner* muss lexikalisch die einen vollständige Definition der vorangehen *Bezeichner* (Wenn eine vollständige Definition; vorhanden ist, andernfalls die Klasse kann nicht verwendet werden außer wie Vorwärts deklarierte) jedoch Vorwärtsdeklarationen der müssen nicht vorausgeht *Bezeichner*. Alle Klassenschlüssel müssen übereinstimmen.

Vollständige Definition: zum Zeitpunkt der vollständigen Definition der Klasse *Bezeichner*, entspricht das Verhalten dem Verhalten wie die Definition der *Bezeichner* deklarierte alle Basisklassen, Member usw. in der Reihenfolge, in der Sie wurden gefunden und in der partiellen Klasse definiert.

Vorlagen: Eine partielle Klasse darf nicht auf eine Vorlage sein.

Generika: Eine partielle Klasse kann generisch sein, wenn die vollständige Definition generisch sein kann. Jede Klasse teilweise oder vollständige muss jedoch genau die gleichen generischen Parameter an, einschließlich formale Parameternamen.

Weitere Informationen zur Verwendung der **teilweise** -Schlüsselwort, finden Sie unter [partielle Klassen (C++ / CX)](http://go.microsoft.com/fwlink/p/?LinkId=249023).

### <a name="requirements"></a>Anforderungen

Compileroption: `/ZW`

## <a name="common-language-runtime"></a>Common Language Runtime

(Diese Sprachfunktion gilt nicht für die Common Language Runtime.)

## <a name="see-also"></a>Siehe auch

[Partielle Klassen (C++ / CX)](http://go.microsoft.com/fwlink/p/?LinkId=249023)