---
title: Ableiten einer Klasse von CObject
ms.date: 11/04/2016
f1_keywords:
- CObject
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
ms.openlocfilehash: 26fdab5165ca098c5d7813ebf44983c261094449
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328440"
---
# <a name="deriving-a-class-from-cobject"></a>Ableiten einer Klasse von CObject

In diesem Artikel wird beschrieben, die mindestens erforderlichen Schritte zum Ableiten einer Klasse von [CObject](../mfc/reference/cobject-class.md). Andere `CObject` Klasse Artikeln wird beschrieben, die erforderlichen Schritte zum Nutzen von bestimmten `CObject` Funktionen wie die Serialisierung und Unterstützung bei der Diagnose Debuggen.

In den erläuterungen zu `CObject`, die Begriffe "Schnittstellendatei" und "Implementierungsdatei" häufig verwendet werden. Die Schnittstellendatei (häufig dem Namen der Headerdatei oder. H-Datei) enthält die Klassendeklaration und andere Informationen zum Verwenden der Klasse erforderlich sind. Die Implementierungsdatei (oder). CPP-Datei) enthält die Definition der Klasse als auch der Code, der die Memberfunktionen von Klassen implementiert. Z. B. für eine Klasse namens `CPerson`, würden Sie in der Regel eine Schnittstellendatei, die mit dem Namen PERSON erstellen. H und eine Implementierungsdatei mit dem Namen "PERSON". CPP. Für einige kleinen Klassen, die nicht zwischen Anwendungen freigegeben werden, ist es jedoch manchmal einfacher, die die Schnittstelle und die Implementierung in einer einzelnen kombinieren. CPP-Datei.

Sie können aus vier Ebenen der Funktionalität beim Ableiten einer Klasse von `CObject`:

- Grundlegende Funktionalität: Keine Unterstützung für die Laufzeit Klasseninformationen oder Serialisierung enthält jedoch die Diagnose Speicherverwaltung.

- Grundlegende Funktionen sowie Unterstützung für die Laufzeit Klasseninformationen.

- Grundlegende Funktionen sowie Unterstützung für die Laufzeit Klasseninformationen und die dynamische Erstellung.

- Grundlegende Funktionen sowie Unterstützung für die Laufzeit Klasseninformationen, dynamische Erstellung und Serialisierung.

Klassen für die Wiederverwendung (diejenigen, die später als Basisklassen verwendet wird) sollten mindestens Laufzeitklasse und Serialisierung unterstützt, einschließen, wenn es sich bei zukünftigen Serialisierungs müssen erwartet wird.

Sie wählen den Umfang der Funktionalität mithilfe von bestimmten Deklaration und Implementierung Makros in der Deklaration und Implementierung der Klassen, die Sie eine von Ableitung `CObject`.

Die folgende Tabelle zeigt die Beziehung zwischen den Makros verwendet, um Serialisierung und Laufzeitinformationen zu unterstützen.

### <a name="macros-used-for-serialization-and-run-time-information"></a>Makros für die Serialisierung und Laufzeitinformationen verwendet

|Makro verwendet|CObject::IsKindOf|CRuntimeClass::<br /><br /> CreateObject|CArchive::operator >><br /><br /> CArchive::operator <<|
|----------------|-----------------------|--------------------------------------|-------------------------------------------------------|
|Grundlegende `CObject` Funktionen|Nein|Nein|Nein|
|`DECLARE_DYNAMIC`|Ja|Nein|Nein|
|`DECLARE_DYNCREATE`|Ja|Ja|Nein|
|`DECLARE_SERIAL`|Ja|Ja|Ja|

#### <a name="to-use-basic-cobject-functionality"></a>Zum Verwenden von CObject-Grundfunktionen

1. Verwenden Sie die normale C++-Syntax, leiten Sie eine Klasse von `CObject` (oder aus einer Klasse abgeleitet `CObject`).

   Das folgende Beispiel zeigt den einfachsten Fall die Ableitung einer Klasse von `CObject`:

   [!code-cpp[NVC_MFCCObjectSample#1](../mfc/codesnippet/cpp/deriving-a-class-from-cobject_1.h)]

In der Regel, möchten Sie jedoch möglicherweise einige der überschreiben `CObject`Member-Funktionen, die Einzelheiten der neuen Klasse behandeln. Angenommen, Sie können in der Regel überschreiben möchten die `Dump` Funktion `CObject` Debugausgabe für den Inhalt der Klasse bereitstellen. Weitere Informationen zum Außerkraftsetzen `Dump`, finden Sie im Artikel [Objekt Dump Anpassung](/previous-versions/visualstudio/visual-studio-2010/sc15kz85(v=vs.100)). Sie sollten auch außer Kraft setzen der `AssertValid` Funktion `CObject` bereitstellen, angepasste testen, um die Konsistenz der Datenmember der Klassenobjekte zu überprüfen. Eine Beschreibung der Außerkraftsetzen `AssertValid`, finden Sie unter [MFC ASSERT_VALID und CObject:: AssertValid](reference/diagnostic-services.md#assert_valid).

Der Artikel [Ebenen von Funktionen angeben](../mfc/specifying-levels-of-functionality.md) beschreibt, wie andere Stufen der Funktionalität, einschließlich der Laufzeit Klasseninformationen, dynamische objekterstellung und Serialisierung.

## <a name="see-also"></a>Siehe auch

[Verwenden von CObject](../mfc/using-cobject.md)
