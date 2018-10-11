---
title: Verwenden von CObject | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- examples [MFC], CObject
- root base class for MFC
- derived classes [MFC], from CObject
- MFC, base class
- CObject class [MFC]
ms.assetid: d0cd19bb-2856-4b41-abbc-620fd64cb223
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 734f9f66a37828b1fed04fc5366dd545e6c5e370
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49082188"
---
# <a name="using-cobject"></a>Verwenden von CObject

[CObject](../mfc/reference/cobject-class.md) ist der Stamm-Basisklasse für die meisten von der Microsoft Foundation Class-Bibliothek (MFC). Die `CObject` -Klasse enthält viele nützliche Features, die Sie in Ihren eigenen Programmobjekten, wie z.B. die Serialisierungsunterstützung und Laufzeit Klasseninformationen Diagnoseausgaben integrieren möchten. Wenn Sie eine Klasse von ableiten `CObject`, Ihre Klasse kann dies ausnutzen `CObject` Funktionen.

## <a name="what-do-you-want-to-do"></a>Was möchten Sie tun

- [Leiten Sie eine Klasse von CObject](../mfc/deriving-a-class-from-cobject.md)

- [Hinzufügen von Unterstützung für die Laufzeit Klasseninformationen, dynamische Erstellung und Serialisierung meiner abgeleiteten Klasse](../mfc/specifying-levels-of-functionality.md)

- [Zugriff zur Laufzeit-Klasseninformationen](../mfc/accessing-run-time-class-information.md)

- [Dynamisches Erstellen von Objekten](../mfc/dynamic-object-creation.md)

- [Sichern Sie die Daten des Objekts zu Diagnosezwecken](/previous-versions/visualstudio/visual-studio-2010/sc15kz85)

- Überprüfen Sie die internen Zustand des Objekts (finden Sie unter [MFC ASSERT_VALID und CObject:: AssertValid](reference/diagnostic-services.md#assert_valid))

- [Haben Sie die Klasse, die sich in den permanenten Speicher serialisieren.](../mfc/serialization-in-mfc.md)

- Eine Liste der [häufig gestellte Fragen zu CObject](../mfc/cobject-class-frequently-asked-questions.md)

## <a name="see-also"></a>Siehe auch

[Konzepte](../mfc/mfc-concepts.md)<br/>
[Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)<br/>
[CRuntimeClass-Struktur](../mfc/reference/cruntimeclass-structure.md)<br/>
[Dateien](../mfc/files-in-mfc.md)<br/>
[Serialisierung](../mfc/serialization-in-mfc.md)

