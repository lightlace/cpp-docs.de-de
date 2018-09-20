---
title: Details zur ATL-Unterstützung hinzugefügt, der ATL-Assistent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.atl.support
dev_langs:
- C++
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: aa66bad0-008f-4886-94c1-2a0a0d04bce4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: efa96037139e61e16b752b45617bb8a3c54be993
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442148"
---
# <a name="details-of-atl-support-added-by-the-atl-wizard"></a>Details zur ATL-Unterstützung, die vom ATL-Assistenten hinzugefügt wird

Wenn Sie [ATL-Unterstützung hinzufügen, um eine vorhandene MFC-Anwendung oder DLL](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), Visual C++ stellt die folgenden Änderungen an der vorhandenen MFC-Projekt (in diesem Beispiel heißt das Projekt `MFCEXE`):

- Es werden zwei neue Dateien (einer IDL-Datei und ein RGS-Datei verwendet, um den Server zu registrieren) hinzugefügt.

- In den Hauptthread der Anwendung Header- und Implementierungsdateien Dateien (Mfcexe.h und Mfcexe.cpp) eine neue Klasse (abgeleitet von `CAtlMFCModule`) hinzugefügt wird. Zusätzlich zu der neuen Klasse Code hinzugefügt `InitInstance` für die Registrierung. Außerdem wird Code hinzugefügt die `ExitInstance` -Funktion für das Klassenobjekt aufheben. In der Headerdatei, schließlich zwei neue Headerdateien (Initguid.h und Mfcexe_i.c) sind enthalten in der Implementierungsdatei, deklarieren und initialisieren die neuen GUIDs für die `CAtlMFCModule`-abgeleitete Klasse.

- Um den Server ordnungsgemäß zu registrieren, wird ein Eintrag für die neue RGS-Datei Ressourcedatei des Projekts hinzugefügt.

## <a name="notes-for-dll-projects"></a>Hinweise für die DLL-Projekten

Wenn Sie ATL-Unterstützung zu einem MFC-DLL-Projekt hinzufügen, sehen Sie einige Unterschiede. Code wird hinzugefügt, um die `DLLRegisterServer` und `DLLUnregisterServer` Funktionen für das Registrieren und Aufheben der Registrierung der DLL. Außerdem wird Code hinzugefügt ["DllCanUnloadNow"](../../atl/reference/catldllmodulet-class.md#dllcanunloadnow) und [DllGetClassObject](../../atl/reference/catldllmodulet-class.md#dllgetclassobject).

## <a name="see-also"></a>Siehe auch

[ATL-Unterstützung in einem MFC-Projekt](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)<br/>
[Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)<br/>
[Hinzufügen einer Memberfunktion](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Adding a Member Variable (Hinzufügen einer Membervariablen)](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Überschreiben einer virtuellen Funktion](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC Message Handler (MFC-Meldungshandler)](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Navigating the Class Structure (Navigieren in der Klassenstruktur)](../../ide/navigating-the-class-structure-visual-cpp.md)
