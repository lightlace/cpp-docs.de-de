---
title: Unterstützung für Aktivierungskontexte im MFC-Modulstatus
ms.date: 11/04/2016
helpviewer_keywords:
- activation contexts [MFC]
- activation contexts [MFC], MFC support
ms.assetid: 1e49eea9-3620-46dd-bc5f-d664749567c7
ms.openlocfilehash: a2e5f56eeb323f1bd5f20c5920bbdbe4a658554d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57267861"
---
# <a name="support-for-activation-contexts-in-the-mfc-module-state"></a>Unterstützung für Aktivierungskontexte im MFC-Modulstatus

MFC erstellt, einen Aktivierungskontext, der mit einer Manifestressource, die vom Benutzermodul bereitgestellt wird. Weitere Informationen dazu, wie Aktivierungskontexte erstellt werden finden Sie unter den folgenden Themen:

- [Aktivierungskontexte](/windows/desktop/SbsCs/activation-contexts)

- [Anwendungsmanifeste](/windows/desktop/SbsCs/application-manifests)

- [Manifesten](/windows/desktop/SbsCs/assembly-manifests)

## <a name="remarks"></a>Hinweise

Wenn Sie diese Windows-SDK-Themen zu lesen, beachten Sie, dass die MFC-Kontext Aktivierungsmechanismus den Aktivierungskontext für die Windows-SDK ähnelt, mit dem Unterschied, dass MFC nicht die Windows SDK-Aktivierung-Kontext-API verwendet.

Aktivierungskontext funktioniert in MFC-Anwendungen, Benutzer-DLLs und MFC-Erweiterungs-DLLs auf folgende Weise:

- MFC-Anwendungen verwenden Ressourcen-ID 1 für die Manifestressource. In diesem Fall die MFC-Bibliothek erstellt keine eigene Aktivierungskontext, verwendet jedoch den Standardkontext für die Anwendung.

- Benutzer der MFC-DLLs verwenden die Ressourcen-ID 2 für die Manifestressource. MFC erstellt, einen Aktivierungskontext für jede Benutzer-DLL, damit anderer Benutzer DLLs verschiedene Versionen derselben Bibliotheken (z. B. die allgemeine Steuerelemente-Bibliothek) verwenden kann.

- MFC-Erweiterungs-DLLs abhängig von den hosting Anwendungen oder Benutzer DLLs, deren Aktivierungskontext erstellen.

Auch wenn der Aktivierungszustand der Kontext geändert werden kann, mithilfe der Prozesse, die unter beschriebenen [mithilfe der Activation-Kontext-API](/windows/desktop/SbsCs/using-the-activation-context-api), mit dem MFC-Aktivierung Kontextmechanismus kann nützlich sein, bei der Entwicklung von DLL-basierten Plug-in-Architekturen ist es nicht einfach (oder nicht möglich) manuell Aktivierungszustand vor und nach einzelne Aufrufe an externe Plug-Ins umschalten.

Der Aktivierungskontext wird erstellt, [AfxWinInit](../mfc/reference/application-information-and-management.md#afxwininit). Es zerstört wird die `AFX_MODULE_STATE` Destruktor. Ein Kontexthandle Aktivierung bleibt `AFX_MODULE_STATE`. (`AFX_MODULE_STATE` finden Sie im [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate).)

Die [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) Makro aktiviert und deaktiviert den Aktivierungskontext. `AFX_MANAGE_STATE` ist für statische MFC-Bibliotheken sowie MFC-DLLs aktiviert, damit MFC-Code in den richtigen Aktivierungskontext ausgewählt, indem die Benutzer-DLL ausführen kann.

## <a name="see-also"></a>Siehe auch

[Aktivierungskontexte](/windows/desktop/SbsCs/activation-contexts)<br/>
[Anwendungsmanifeste](/windows/desktop/SbsCs/application-manifests)<br/>
[Manifesten](/windows/desktop/SbsCs/assembly-manifests)<br/>
[AfxWinInit](../mfc/reference/application-information-and-management.md#afxwininit)<br/>
[AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate)<br/>
[AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state)
