---
title: Details der ATL-Unterstützung hinzugefügt, durch die ATL-Assistent | Microsoft Docs
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
ms.openlocfilehash: 7ffe43c33e4b371f6d5dcf5dc7da327b11328af7
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121378"
---
# <a name="details-of-atl-support-added-by-the-atl-wizard"></a>Details zur ATL-Unterstützung, die vom ATL-Assistenten hinzugefügt wird
Wenn Sie [ATL-Unterstützung hinzufügen, um eine vorhandene MFC-Anwendung oder DLL](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), Visual C++ stellt die folgenden Änderungen an der vorhandenen MFC-Projekt (in diesem Beispiel heißt das Projekt `MFCEXE`):  
  
-   Zwei neue Dateien (eine IDL-Datei und ein RGS-Datei verwendet, um den Server registrieren) hinzugefügt werden.  
  
-   In der hauptanwendung Header und Implementierung (Mfcexe.h und Mfcexe.cpp) eine neue Klasse (abgeleitet von `CAtlMFCModule`) hinzugefügt wird. Zusätzlich zu der neuen Klasse Code hinzugefügt wird `InitInstance` für die Registrierung. Außerdem wird Code hinzugefügt die `ExitInstance` Funktion zum Aufheben der Klassenobjekt. In der Headerdatei schließlich zwei neue Headerdateien (Initguid.h und Mfcexe_i.c) sind enthalten in der Implementierungsdatei, deklarieren und initialisieren die neue GUIDs für die `CAtlMFCModule`-Klasse.  
  
-   Zum Registrieren des Servers ordnungsgemäß, wird dem Projekt die Ressourcendatei enthält ein Eintrag für die neue RGS-Datei hinzugefügt.  
  
## <a name="notes-for-dll-projects"></a>Anmerkungen zu dieser DLL-Projekten  
 Wenn Sie ein MFC-DLL-Projekt ATL-Unterstützung hinzugefügt haben, sehen Sie einige Unterschiede. Code wird hinzugefügt, um die `DLLRegisterServer` und `DLLUnregisterServer` Funktionen zum Registrieren und Aufheben der Registrierung der DLL. Außerdem wird Code hinzugefügt [DllCanUnloadNow](../../atl/reference/catldllmodulet-class.md#dllcanunloadnow) und [DllGetClassObject](../../atl/reference/catldllmodulet-class.md#dllgetclassobject).  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-Unterstützung in MFC-Projekt](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)   
 [Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Adding a Class (Hinzufügen einer Klasse)](../../ide/adding-a-class-visual-cpp.md)   
 [Hinzufügen einer Memberfunktion](../../ide/adding-a-member-function-visual-cpp.md)   
 [Adding a Member Variable (Hinzufügen einer Membervariablen)](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Overriding a Virtual Function (Überschreiben einer virtuellen Funktion)](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC Message Handler (MFC-Meldungshandler)](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navigating the Class Structure (Navigieren in der Klassenstruktur)](../../ide/navigating-the-class-structure-visual-cpp.md)
