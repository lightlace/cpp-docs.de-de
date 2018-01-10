---
title: Ableiten einer Klasse von CObject | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CObject
dev_langs: C++
helpviewer_keywords:
- DECLARE_DYNCREATE macro [MFC]
- DECLARE_SERIAL macro [MFC]
- macros [MFC], serialization
- serialization [MFC], macros
- DECLARE_DYNAMIC macro [MFC]
- derived classes [MFC], from CObject
- CObject class [MFC], deriving serializable classes
- CObject class [MFC], deriving from
ms.assetid: 5ea4ea41-08b5-4bd8-b247-c5de8c152a27
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 97e151d8c3ec44286807baf5e68d4e4eac17e306
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="deriving-a-class-from-cobject"></a>Ableiten einer Klasse von CObject
Dieser Artikel beschreibt die erforderlichen Schritte zum Ableiten einer Klasse von [CObject](../mfc/reference/cobject-class.md). Andere `CObject` Klasse Artikel beschreiben die erforderlichen Schritte zum Nutzen von bestimmten `CObject` Funktionen, z. B. Serialisierung und Unterstützung bei der Diagnose Debuggen.  
  
 In den Diskussionen `CObject`, die Begriffe "Schnittstellendatei" und "Implementierungsdatei" häufig verwendet werden. Die Schnittstellendatei (häufig aufgerufen, die Headerdatei oder. H-Datei) enthält die Klassendeklaration und andere Informationen zum Verwenden der Klasse erforderlich sind. Der Implementierungsdatei (oder). CPP-Datei) enthält die Definition der Klasse als auch den Code, der die Memberfunktionen von Klassen implementiert. Z. B. für eine Klasse namens `CPerson`, würden Sie in der Regel eine Schnittstellendatei mit dem Namen PERSON erstellen. H und einer Implementierungsdatei mit dem Namen "PERSON". CPP. Für einige kleineren Klassen, die nicht für mehrere Anwendungen freigegeben werden, ist es jedoch in einigen Fällen einfacher, die Schnittstelle und die Implementierung in einer einzelnen kombinieren. CPP-Datei.  
  
 Ihnen stehen vier Grade an Funktionalität beim Ableiten einer Klasse von `CObject`:  
  
-   Grundlegende Funktionalität: keine Unterstützung für Laufzeit Klasseninformationen oder der Serialisierung umfasst jedoch diagnostische Speicherverwaltung.  
  
-   Grundlegende Funktionen sowie Unterstützung für Laufzeit Klasseninformationen.  
  
-   Grundlegende Funktionen sowie Unterstützung für Laufzeit Klasseninformationen und dynamische Erstellung.  
  
-   Grundlegende Funktionen sowie Unterstützung für Laufzeit Klasseninformationen, dynamische Erstellung und Serialisierung.  
  
 Klassen für die Wiederverwendung (diejenigen, die später als Basisklassen verwendet werden) sollten mindestens Run-Time-Klasse und Serialisierung unterstützt, einschließen, wenn jede benötigte zukünftige Serialisierung erwartet wird.  
  
 Sie wählen das Maß an Funktionalität mithilfe von bestimmten Deklaration und Implementierung Makros in die Deklaration und Implementierung der Klassen von ableiten `CObject`.  
  
 Die folgende Tabelle zeigt die Beziehung zwischen den Makros verwendet, um Serialisierung und Laufzeitinformationen zu unterstützen.  
  
### <a name="macros-used-for-serialization-and-run-time-information"></a>Makros, die für die Serialisierung und Laufzeitinformationen verwendet  
  
|-Makro verwendet|CObject:: IsKindOf|CRuntimeClass::<br /><br /> CreateObject|CArchive::operator >><br /><br /> CArchive::operator <<|  
|----------------|-----------------------|--------------------------------------|-------------------------------------------------------|  
|Grundlegende `CObject` Funktionalität|Nein|Nein|Nein|  
|`DECLARE_DYNAMIC`|Ja|Nein|Nein|  
|`DECLARE_DYNCREATE`|Ja|Ja|Nein|  
|`DECLARE_SERIAL`|Ja|Ja|Ja|  
  
#### <a name="to-use-basic-cobject-functionality"></a>Zum Verwenden von CObject Grundfunktionen  
  
1.  Verwenden Sie die normale C++-Syntax, leiten Sie eine Klasse von `CObject` (oder von einer Klasse abgeleitet `CObject`).  
  
     Das folgende Beispiel zeigt den einfachsten Fall die Ableitung einer Klasse von `CObject`:  
  
     [!code-cpp[NVC_MFCCObjectSample#1](../mfc/codesnippet/cpp/deriving-a-class-from-cobject_1.h)]  
  
 In der Regel wird, möchten Sie jedoch möglicherweise einige der überschreiben `CObject`Memberfunktionen, die Einzelheiten für die neue Klasse zu behandeln. Angenommen, Sie können in der Regel überschreiben möchten die `Dump` Funktion `CObject` Debugausgabe für den Inhalt der Klasse angeben. Weitere Informationen zum Außerkraftsetzen `Dump`, finden Sie im Artikel [Diagnose: Objektdumps](http://msdn.microsoft.com/en-us/727855b1-5a83-44bd-9fe3-f1d535584b59). Möchten Sie möglicherweise auch überschreiben die `AssertValid` Funktion der `CObject` um angepasste testen, um zu überprüfen, ob die Konsistenz der Datenmember von Klassenobjekten bereitzustellen. Eine Beschreibung zum Überschreiben von `AssertValid`, finden Sie unter [MFC ASSERT_VALID und CObject:: AssertValid](http://msdn.microsoft.com/en-us/7654fb75-9e9a-499a-8165-0a96faf2d5e6).  
  
 Der Artikel [Ebenen von Funktionen angeben](../mfc/specifying-levels-of-functionality.md) wird beschrieben, wie auf anderen Ebenen von Funktionen, einschließlich der Laufzeit Klasseninformationen, dynamische objekterstellung und Serialisierung angeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CObject](../mfc/using-cobject.md)

