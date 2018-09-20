---
title: OLE-Automatisierungsklassen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- Automation, classes
- Automation classes [MFC], OLE classes
- OLE Automation [MFC], classes
- Automation classes [MFC]
- OLE Automation [MFC]
ms.assetid: 96e5372b-ff8a-4da1-933b-4d9bbf4dceb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ea35e51296b2fc528657c4dd9f9b9b76b84aae83
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391513"
---
# <a name="ole-automation-classes"></a>OLE-Automatisierungsklassen

Diese Klassen unterstützen die Benutzeroberflächenautomatisierungs-Clients (Anwendungen, die Steuern von anderen Anwendungen). Automatisierungsserver (Anwendungen, die von anderen Anwendungen gesteuert werden können) werden über unterstützt [Dispatchzuordnungen](../mfc/reference/dispatch-maps.md).

[COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md)<br/>
Zum Aufrufen von Automatisierungsserver aus Ihrem Automatisierungsclient verwendet. Wenn Sie eine Klasse hinzufügen, wird diese Klasse verwendet, zum Erstellen von typsicheren Klassen für Automatisierungsserver, die eine Typbibliothek zu bieten.

[COleDispatchException](../mfc/reference/coledispatchexception-class.md)<br/>
Eine Ausnahme aufgrund eines Fehlers während der OLE-Automatisierung. Automation-Ausnahmen werden vom Automatisierungsserver ausgelöst und abgefangen, die von Benutzeroberflächenautomatisierungs-Clients.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)

