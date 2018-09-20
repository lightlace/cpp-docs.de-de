---
title: 'Automatisierungsserver: Probleme mit der Objektlebensdauer | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], lifetime
- lifetime, automation server
- Automation servers, object lifetime
- servers, lifetime of Automation
ms.assetid: 342baacf-4015-4a0e-be2f-321424f1cb43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a53d1a9d3849798fa1e583c0758b156d282a401c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46397116"
---
# <a name="automation-servers-object-lifetime-issues"></a>Automatisierungsserver: Probleme mit der Objektlebensdauer

Wenn ein Automatisierungsclient erstellt oder ein OLE-Element aktiviert, übergibt der Server auf dieses Objekt einen Zeiger an dem Client. Der Client richtet einen Verweis auf das Objekt durch einen Aufruf an die OLE-Funktion [IUnknown:: AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref). Dieser Verweis gültig ist, bis der Client ruft [IUnknown:: Release](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release). (Clientanwendungen, die geschrieben werden, mit der Microsoft Foundation Class Library-OLE-Klassen müssen diese Aufrufe nicht; das Framework erfolgt.) Das OLE-System und der Server selbst können Verweise auf das Objekt festgelegt werden. Ein Server sollte nicht Zerstören eines Objekts als externe Verweise auf das Objekt weiterhin gültig bleiben.

Das Framework verwaltet eine interne Anzahl die Anzahl der Verweise auf alle Serverobjekt, das von abgeleiteten [CCmdTarget](../mfc/reference/ccmdtarget-class.md). Diese Anzahl wird aktualisiert, wenn ein Automation-Client oder eine andere Entität hinzufügt, oder gibt einen Verweis auf das Objekt frei.

Wenn der Verweiszähler 0 ist, wird das Framework Ruft die virtuelle Funktion [CCmdTarget::OnFinalRelease](../mfc/reference/ccmdtarget-class.md#onfinalrelease). Ruft die standardmäßige Implementierung dieser Funktion die **löschen** Operator, um das Objekt gelöscht werden.

Die Microsoft Foundation Class-Bibliothek bietet zusätzliche Funktionen zum Steuern des Anwendungsverhaltens aus, wenn externe Clients Verweise auf Objekte von der Anwendung. Neben der verwalten die Anzahl der Verweise auf jedes Objekt, Wartung von Servern eine globale Anzahl von aktiven Objekten. Die globalen Funktionen [AfxOleLockApp](../mfc/reference/application-control.md#afxolelockapp) und [AfxOleUnlockApp](../mfc/reference/application-control.md#afxoleunlockapp) der Anwendung die Anzahl von aktiven Objekten zu aktualisieren. Wenn diese Zahl ungleich NULL ist, wird die Anwendung nicht beendet, wenn der Benutzer schließen aus dem Systemmenü oder beenden aus dem Menü "Datei" auswählt. Stattdessen ist das Hauptfenster der Anwendung ausgeblendet (jedoch nicht zerstört) bis alle ausstehenden Client-Anforderungen abgeschlossen wurden. In der Regel `AfxOleLockApp` und `AfxOleUnlockApp` heißen in den Konstruktoren und Destruktoren, bzw. von Klassen, die Unterstützung der Automatisierung.

In einigen Fällen erzwingen Umstände den Server beendet, während ein Client noch einen Verweis auf ein Objekt enthält. Beispielsweise kann eine Ressource, von der die Server abhängig ist, nicht verfügbar ist, tritt ein Fehler auf den Server verursacht werden. Der Benutzer kann auch Serverdokument schließen, die Objekte enthält, auf die anderen Anwendungen Verweise haben.

Im Windows SDK finden Sie unter `IUnknown::AddRef` und `IUnknown::Release`.

## <a name="see-also"></a>Siehe auch

[Automatisierungsserver](../mfc/automation-servers.md)<br/>
[AfxOleCanExitApp](../mfc/reference/application-control.md#afxolecanexitapp)

