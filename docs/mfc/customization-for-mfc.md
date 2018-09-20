---
title: Anpassung für MFC | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- customizations, MFC Extensions
ms.assetid: 3b1b7532-8cc9-48dc-9bbe-7fd4060530b5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 640d6726623e8fb6d563153823f449f7caefcf30
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385000"
---
# <a name="customization-for-mfc"></a>Anpassung für MFC

Dieses Thema enthält Tipps zum Anpassen einer MFC-Anwendung.

## <a name="general-customizations"></a>Allgemeine Anpassungen

Sie können speichern und laden den Status Ihrer Anwendung in der Registrierung. Wenn Sie diese Option aktivieren, wird die Anwendung ihren ursprünglichen Zustand aus der Registrierung geladen. Wenn Sie das anfängliche docking-Layout für Ihre Anwendung ändern, müssen Sie die Registrierungsdaten für Ihre Anwendung zu löschen. Andernfalls überschreibt die Daten in der Registrierung alle Änderungen, die an das anfängliche Layout vorgenommen.

## <a name="class-specific-customizations"></a>Mandantenklassen geltenden Schemaanpassungen-Anpassungen

Zusätzliche Anpassungstipps finden Sie in den folgenden Themen:

- [CBasePane-Klasse](../mfc/reference/cbasepane-class.md)

- [CDockablePane-Klasse](../mfc/reference/cdockablepane-class.md)

- [CDockingManager-Klasse](../mfc/reference/cdockingmanager-class.md)

- [CMFCBaseTabCtrl-Klasse](../mfc/reference/cmfcbasetabctrl-class.md)

## <a name="additional-customization-tips"></a>Zusätzliche Anpassungstipps

[Anpassen von Tastatur und Maus](../mfc/keyboard-and-mouse-customization.md)

[Benutzerdefinierte Tools](../mfc/user-defined-tools.md)

## <a name="see-also"></a>Siehe auch

[MFC-Desktopanwendungen](../mfc/mfc-desktop-applications.md)<br/>
[Sicherheitsauswirkungen der Anpassung](../mfc/security-implications-of-customization.md)

