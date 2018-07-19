---
title: Benachrichtigungshooks | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, notification hooks
ms.assetid: e9c291ed-2f2d-4319-a171-09800625256f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0210c4ee058694594893a029789442c89003da2e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377818"
---
# <a name="notification-hooks"></a>Benachrichtigungshooks
Die Benachrichtigungshooks werden aufgerufen, kurz bevor die folgenden Aktionen, in die Hilfsroutine hat ausgeführt werden:  
  
-   Das gespeicherte Handle für die Bibliothek wird überprüft, um festzustellen, ob sie bereits geladen wurde.  
  
-   **LoadLibrary** wird aufgerufen, um die DLL zu laden.  
  
-   **GetProcAddress** wird aufgerufen, um zu versuchen, erhalten die Adresse der Prozedur.  
  
-   Zurück zum Thunk Verzögerung importieren.  
  
 Der Benachrichtigungshook aktiviert ist:  
  
-   Indem Sie eine neue Definition des Zeigers **__pfnDliNotifyHook2** , um auf Ihre eigene Funktion zu verweisen, die Benachrichtigungen empfangenden initialisiert wird.  
  
     - oder -   
  
-   Durch Festlegen des Zeigers **__pfnDliNotifyHook2** auf die Hookfunktion, bevor Aufrufe an die DLL, die das Programm ist laden verzögern.  
  
 Wenn die Benachrichtigung ist **DliStartProcessing**, kann die Hookfunktion zurückgeben:  
  
 NULL  
 Die Standard-Hilfsprogramm verarbeitet das Laden der DLL. Dies ist hilfreich, die nur für Informationszwecke aufgerufen werden.  
  
 Funktionszeiger  
 Das verzögerte Laden Standardbehandlung zu umgehen. Dadurch können Sie einen eigenen Handler laden angeben.  
  
 Wenn die Benachrichtigung ist **DliNotePreLoadLibrary**, kann die Hookfunktion zurückgeben:  
  
-   0, wenn er nur zu Informationszwecken Benachrichtigungen will.  
  
-   Das HMODULE für geladenen DLL, wenn sie die DLL selbst geladen.  
  
 Wenn die Benachrichtigung ist **DliNotePreGetProcAddress**, kann die Hookfunktion zurückgeben:  
  
-   0, wenn er nur zu Informationszwecken Benachrichtigungen will.  
  
-   Importiert die Adresse der Funktion, wenn die Hookfunktion die Adresse selbst abruft.  
  
 Wenn die Benachrichtigung ist **um DliNoteEndProcessing**, die Hookfunktion Rückgabewert wird ignoriert.  
  
 Wenn dieser Zeiger (ungleich null) initialisiert wird, wird die Hilfsfunktion für verzögertes Laden Aufrufen der Funktion an bestimmten Punkten Benachrichtigung während seiner Ausführung. Der Funktionszeiger ist wie folgt definiert:  
  
```  
// The "notify hook" gets called for every call to the  
// delay load helper.  This allows a user to hook every call and  
// skip the delay load helper entirely.  
//  
// dliNotify == {  
//  dliStartProcessing |  
//  dliNotePreLoadLibrary  |  
//  dliNotePreGetProc |  
//  dliNoteEndProcessing}  
//  on this call.  
//  
ExternC  
PfnDliHook   __pfnDliNotifyHook2;  
  
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}  
ExternC  
PfnDliHook   __pfnDliFailureHook2;  
```  
  
 Übergeben Sie die Benachrichtigungen eine **DelayLoadInfo** -Struktur mit die Hookfunktion zusammen mit der Benachrichtigung-Wert. Diese Daten sind identisch mit dem von der Hilfsfunktion für verzögertes Laden verwendet. Die Benachrichtigung Werte werden in definierten Werte werden [Struktur- und Konstantendefinitionen](../../build/reference/structure-and-constant-definitions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Fehlerbehandlung und Benachrichtigung](../../build/reference/error-handling-and-notification.md)