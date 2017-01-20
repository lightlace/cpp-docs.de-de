---
title: "Benachrichtigungshooks"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Verzögertes Laden von DLLs, Benachrichtigungshooks"
ms.assetid: e9c291ed-2f2d-4319-a171-09800625256f
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Benachrichtigungshooks
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Benachrichtigungshooks werden aufgerufen, unmittelbar bevor in der Hilfsroutine die folgenden Aktionen durchgeführt werden:  
  
-   Das gespeicherte Handle auf die Bibliothek wird überprüft, um festzustellen, ob diese bereits geladen wurde.  
  
-   LoadLibrary wird aufgerufen, um die DLL zu laden.  
  
-   GetProcAddress wird aufgerufen, um die Prozeduradresse abzurufen.  
  
-   Kehren Sie zum verzögert geladenen Import\-Thunk zurück.  
  
 Der Benachrichtigungshook wird wie folgt aktiviert:  
  
-   Durch Bereitstellen einer neuen Definition des **\_\_pfnDliNotifyHook2**\-Zeigers, der so initialisiert wurde, dass er auf die eigene Funktion für den Empfang von Benachrichtigungen zeigt,  
  
     \- oder \-  
  
-   durch Festlegen des **\_\_pfnDliNotifyHook2**\-Zeigers auf die Hookfunktion, bevor Aufrufe der DLL erfolgen, die vom Programm verzögert geladen werden.  
  
 Handelt es sich bei der Benachrichtigung um **dliStartProcessing**, können von der Hookfunktion folgende Werte zurückgegeben werden:  
  
 NULL  
 Das Laden der DLL wird von der Standardhilfsfunktion behandelt.  Dieser Aufruf ist nur zu Informationszwecken sinnvoll.  
  
 Funktionszeiger  
 Die Standardbehandlung des verzögerten Ladens wird umgangen.  Hiermit können Sie einen eigenen Ladehandler bereitstellen.  
  
 Handelt es sich bei der Benachrichtigung um **dliNotePreLoadLibrary**, können von der Hookfunktion folgende Werte zurückgegeben werden:  
  
-   0, falls nur Informationsbenachrichtigungen erwünscht sind.  
  
-   das **HMODULE** für die geladene DLL, falls die DLL von ihm selbst geladen wurde.  
  
 Handelt es sich bei der Benachrichtigung um **dliNotePreGetProcAddress**, können von der Hookfunktion folgende Werte zurückgegeben werden:  
  
-   0, falls nur Informationsbenachrichtigungen erwünscht sind.  
  
-   die Adresse der importierten Funktion, falls die Adresse von der Hookfunktion abgerufen wurde.  
  
 Handelt es sich bei der Benachrichtigung um **dliNoteEndProcessing**, wird der Rückgabewert der Hookfunktion ignoriert.  
  
 Wenn dieser Zeiger mit einem Wert ungleich 0 \(null\) initialisiert ist, wird die Funktion von der Hilfsfunktion für verzögertes Laden an bestimmten Benachrichtigungspunkten gestartet, während die Hilfsfunktion ausgeführt wird.  Der Funktionszeiger weist folgende Definition auf:  
  
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
  
 Die Benachrichtigungen werden in einer **DelayLoadInfo**\-Struktur zusammen mit dem Benachrichtigungswert an die Hookfunktion übergeben.  Es werden dieselben Daten verwendet wie bei der Hilfsroutine für verzögertes Laden.  Die möglichen Benachrichtigungswerte sind unter [Struktur\- und Konstantendefinitionen](../../build/reference/structure-and-constant-definitions.md) definiert.  
  
## Siehe auch  
 [Fehlerbehandlung und Benachrichtigung](../../build/reference/error-handling-and-notification.md)