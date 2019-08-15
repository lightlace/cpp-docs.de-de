---
title: 'Automatisierungsserver: Probleme mit der Objekt Lebensdauer'
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], lifetime
- lifetime, automation server
- Automation servers, object lifetime
- servers, lifetime of Automation
ms.assetid: 342baacf-4015-4a0e-be2f-321424f1cb43
ms.openlocfilehash: 74b4bf87b512d35c99942f4aa36174a8673079c5
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509189"
---
# <a name="automation-servers-object-lifetime-issues"></a>Automatisierungsserver: Probleme mit der Objekt Lebensdauer

Wenn ein Automatisierungs Client ein OLE-Element erstellt oder aktiviert, übergibt der Server dem Client einen Zeiger auf das Objekt. Der Client erstellt einen Verweis auf das Objekt, indem er die OLE-Funktion [IUnknown:: adressf](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)aufruft. Dieser Verweis ist wirksam, bis der Client [IUnknown:: Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)aufruft. (Bei Client Anwendungen, die mit den OLE-Klassen der Microsoft Foundation Class-Bibliothek geschrieben wurden, müssen diese Aufrufe nicht durchführt werden. Das OLE-System und der Server selbst können Verweise auf das Objekt erstellen. Ein Server sollte ein Objekt nicht zerstören, solange externe Verweise auf das Objekt in Kraft bleiben.

Das Framework verwaltet eine interne Anzahl von Verweisen auf ein beliebiges Server Objekt, das von [CCmdTarget](../mfc/reference/ccmdtarget-class.md)abgeleitet ist. Diese Anzahl wird aktualisiert, wenn ein Automation-Client oder eine andere Entität einen Verweis auf das-Objekt hinzufügt oder freigibt.

Wenn der Verweis Zähler auf 0 festgelegt wird, ruft das Framework die virtuelle Funktion [CCmdTarget:: OnFinalRelease](../mfc/reference/ccmdtarget-class.md#onfinalrelease)auf. Die Standard Implementierung dieser Funktion Ruft den **Delete** -Operator auf, um dieses Objekt zu löschen.

Der Microsoft Foundation Class-Bibliothek bietet zusätzliche Funktionen zum Steuern des Anwendungs Verhaltens, wenn externe Clients Verweise auf die Objekte der Anwendung haben. Neben der Beibehaltung der Anzahl der Verweise auf jedes Objekt behalten die Server eine globale Anzahl aktiver Objekte bei. Die globalen Funktionen [AfxOleLockApp](../mfc/reference/application-control.md#afxolelockapp) und [AfxOleUnlockApp](../mfc/reference/application-control.md#afxoleunlockapp) aktualisieren die Anzahl aktiver Objekte der Anwendung. Wenn diese Anzahl nicht 0 (null) ist, wird die Anwendung nicht beendet, wenn der Benutzer im Menü "System" die Option schließen auswählt oder im Menü Datei auf Beenden klickt. Stattdessen wird das Hauptfenster der Anwendung ausgeblendet (aber nicht zerstört), bis alle ausstehenden Client Anforderungen abgeschlossen sind. In der Regel `AfxOleUnlockApp` werden undindenKonstruktorenbzw.debugktorenvonKlassenaufgerufen,dieAutomationunterstützen.`AfxOleLockApp`

Manchmal erzwingen Umstände, dass der Server beendet wird, während ein Client noch über einen Verweis auf ein Objekt verfügt. Beispielsweise kann eine Ressource, von der der Server abhängt, möglicherweise nicht mehr verfügbar sein, sodass auf dem Server ein Fehler auftritt. Der Benutzer kann auch ein Server Dokument schließen, das Objekte enthält, auf die andere Anwendungen verweisen.

Informationen zum Windows SDK finden `IUnknown::AddRef` Sie unter und. `IUnknown::Release`

## <a name="see-also"></a>Siehe auch

[Automatisierungsserver](../mfc/automation-servers.md)<br/>
[AfxOleCanExitApp](../mfc/reference/application-control.md#afxolecanexitapp)
