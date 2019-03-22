---
title: Verwenden von CObject
ms.date: 11/04/2016
f1_keywords:
- CObject
helpviewer_keywords:
- examples [MFC], CObject
- root base class for MFC
- derived classes [MFC], from CObject
- MFC, base class
- CObject class [MFC]
ms.assetid: d0cd19bb-2856-4b41-abbc-620fd64cb223
ms.openlocfilehash: 6c4355f43df33f37838cfc9be4453e42271ae9f3
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328479"
---
# <a name="using-cobject"></a>Verwenden von CObject

[CObject](../mfc/reference/cobject-class.md) ist die Stamm-Basisklasse für die meisten Objekte der Microsoft Foundation Class-Bibliothek (MFC). Die `CObject` -Klasse enthält viele nützliche Features, wie z.B. die Serialisierungsunterstützung, Laufzeit Klasseninformationen und Diagnoseausgaben, die Sie in Ihren eigenen Programmobjekten integrieren können. Wenn Sie eine Klasse von ableiten `CObject`, Ihre Klasse kann dies ausnutzen `CObject` Funktionen.

## <a name="what-do-you-want-to-do"></a>Was möchten Sie tun

- [Leiten Sie eine Klasse von CObject ab](../mfc/deriving-a-class-from-cobject.md)

- [Hinzufügen von Unterstützung für die Laufzeit Klasseninformationen, dynamische Erstellung und Serialisierung meiner abgeleiteten Klasse](../mfc/specifying-levels-of-functionality.md)

- [Zugriff auf Laufzeit-Klasseninformationen](../mfc/accessing-run-time-class-information.md)

- [Dynamisches Erstellen von Objekten](../mfc/dynamic-object-creation.md)

- [Sichern Sie die Daten des Objekts zu Diagnosezwecken](/previous-versions/visualstudio/visual-studio-2010/sc15kz85(v=vs.100))

- Überprüfen Sie den internen Zustand des Objekts (zu finden unter [MFC ASSERT_VALID und CObject:: AssertValid](reference/diagnostic-services.md#assert_valid))

- [Erstellen einer Klasse, die sich in den permanenten Speicher serialisiert.](../mfc/serialization-in-mfc.md)

- Eine Liste der [häufig gestellten Fragen zu CObject](../mfc/cobject-class-frequently-asked-questions.md)

## <a name="see-also"></a>Siehe auch

[Konzepte](../mfc/mfc-concepts.md)<br/>
[Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)<br/>
[CRuntimeClass-Struktur](../mfc/reference/cruntimeclass-structure.md)<br/>
[Dateien](../mfc/files-in-mfc.md)<br/>
[Serialisierung](../mfc/serialization-in-mfc.md)
