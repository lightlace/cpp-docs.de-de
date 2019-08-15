---
title: Unterstützung für Aktivierungskontexte im MFC-Modulstatus
ms.date: 11/04/2016
helpviewer_keywords:
- activation contexts [MFC]
- activation contexts [MFC], MFC support
ms.assetid: 1e49eea9-3620-46dd-bc5f-d664749567c7
ms.openlocfilehash: 296df3d2ecec74c5c9a7deef1617298d40243724
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511430"
---
# <a name="support-for-activation-contexts-in-the-mfc-module-state"></a>Unterstützung für Aktivierungskontexte im MFC-Modulstatus

MFC erstellt mithilfe einer Manifestressource, die vom Benutzermodul bereitgestellt wird, einen Aktivierungs Kontext. Weitere Informationen zum Erstellen von Aktivierungs Kontexten finden Sie in den folgenden Themen:

- [Aktivierungs Kontexte](/windows/win32/SbsCs/activation-contexts)

- [Anwendungs Manifeste](/windows/win32/SbsCs/application-manifests)

- [Assembly-Manifeste](/windows/win32/SbsCs/assembly-manifests)

## <a name="remarks"></a>Hinweise

Beachten Sie beim Lesen dieser Windows SDK Themen, dass der MFC-Aktivierungs Kontext Mechanismus dem Windows SDK Aktivierungs Kontext ähnelt, mit dem Unterschied, dass MFC die Windows SDK Aktivierungs Kontext-API nicht verwendet.

Der Aktivierungs Kontext funktioniert in MFC-Anwendungen, Benutzer-DLLs und MFC-Erweiterungs-DLLs wie folgt:

- MFC-Anwendungen verwenden die Ressourcen-ID 1 für Ihre Manifestressource. In diesem Fall erstellt der MFC keinen eigenen Aktivierungs Kontext, sondern verwendet den Standard Anwendungskontext.

- MFC-Benutzer-DLLs verwenden die Ressourcen-ID 2 für Ihre Manifestressource. Hier erstellt MFC einen Aktivierungs Kontext für jede Benutzer-dll, sodass verschiedene Benutzer-DLLs verschiedene Versionen derselben Bibliotheken verwenden können (z. b. die Bibliothek für allgemeine Steuerelemente).

- MFC-Erweiterungs-DLLs basieren auf Ihren Hostinganwendungen oder Benutzer-DLLs, um Ihren Aktivierungs Kontext einzurichten.

Obwohl der Aktivierungs Kontext Zustand mit den unter [Verwenden der Aktivierungs Kontext-API](/windows/win32/SbsCs/using-the-activation-context-api)beschriebenen Prozessen geändert werden kann, kann die Verwendung des MFC-Aktivierungs Kontext Mechanismus nützlich sein, wenn Sie dll-basierte Plug-in-Architekturen entwickeln, bei denen es nicht einfach ist (oder nicht möglich), um den Aktivierungszustand vor und nach einzelnen Aufrufen externer Plug-ins manuell zu wechseln.

Der Aktivierungs Kontext wird in [afxwininit](../mfc/reference/application-information-and-management.md#afxwininit)erstellt. Sie wird im `AFX_MODULE_STATE` Dekonstruktor zerstört. Ein Aktivierungs Kontext Handle wird in `AFX_MODULE_STATE`beibehalten. (`AFX_MODULE_STATE` wird in [afxgetstaticmodulestate](reference/extension-dll-macros.md#afxgetstaticmodulestate)beschrieben.)

Das [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) -Makro aktiviert und deaktiviert den Aktivierungs Kontext. `AFX_MANAGE_STATE`ist sowohl für statische MFC-Bibliotheken als auch für MFC-DLLs aktiviert, damit MFC-Code im richtigen Aktivierungs Kontext ausgeführt werden kann, der von der Benutzer-DLL ausgewählt wird.

## <a name="see-also"></a>Siehe auch

[Aktivierungs Kontexte](/windows/win32/SbsCs/activation-contexts)<br/>
[Anwendungs Manifeste](/windows/win32/SbsCs/application-manifests)<br/>
[Assembly-Manifeste](/windows/win32/SbsCs/assembly-manifests)<br/>
[AfxWinInit](../mfc/reference/application-information-and-management.md#afxwininit)<br/>
[Afxgetstaticmodulestate](reference/extension-dll-macros.md#afxgetstaticmodulestate)<br/>
[AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state)
