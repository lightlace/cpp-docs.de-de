---
title: Beschränkungen für das verzögerte Laden von DLLs | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- constraints [C++], delayed loading of DLLs
- delayed loading of DLLs, constraints
- DLLs [C++], constraints
ms.assetid: 0097ff65-550f-4a4e-8ac3-39bf6404f926
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 213a7c32204b8f96969b4ad7a94683916b66db10
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43200841"
---
# <a name="constraints-of-delay-loading-dlls"></a>Beschränkungen für das verzögerte Laden von DLLs
Es gibt Einschränkungen hinsichtlich des verzögerten Ladens von Importen.  
  
-   Datenimporte können nicht unterstützt werden. Eine Problemumgehung besteht darin, den Datenimport explizit über `LoadLibrary` (oder `GetModuleHandle`, wenn Sie wissen, dass die Hilfsfunktion für das verzögerte Laden die DLL geladen hat) und `GetProcAddress` selbst zu handhaben.  
  
-   Ein verzögertes Laden von Kernel32.dll wird nicht unterstützt. Diese DLL ist erforderlich, damit die Routinen der Hilfsfunktion für das verzögerte Laden das verzögerte Laden durchführen können.  
  
-   [Binden von](../../build/reference/binding-imports.md) des Eintrags an, die weitergeleitet werden, wird nicht unterstützt.  
  
-   Das verzögerte Laden einer DLL führt möglicherweise nicht zum selben Verwalten des Prozesses, wenn pro Prozess stattfindende Initialisierungen vorhanden sind, die am Einstiegspunkt der verzögert geladenen DLL stattfinden. Anderen Fällen gehört der statische TLS (Thread local Storage), die mithilfe von deklariert [__declspec(thread)](../../cpp/thread.md), die nicht behandelt, wenn die DLL, über geladen wird `LoadLibrary`. Der dynamische TLS ist über `TlsAlloc`, `TlsFree`, `TlsGetValue` und `TlsSetValue` immer noch zur Verwendung in statischen oder verzögert geladenen DLLs verfügbar.  
  
-   Statische (globale) Funktionszeiger sollten für importierte Funktionen erneut initialisiert werden, nach die Funktion erstmals aufgerufen wurde. Der Grund ist, dass der Funktionszeiger bei der ersten Verwendung auf den Thunk zeigt.  
  
-   Derzeit gibt es keine Möglichkeit, das Laden nur bestimmter Verfahren aus einer DLL bei Verwendung des normalen Importmechanismus zu verzögern.  
  
-   Benutzerdefinierte Aufrufkonventionen (wie die Verwendung von Bedingungscodes in x86-Architekturen) werden nicht unterstützt. Außerdem werden die Gleitkommaregister auf keiner Plattform gespeichert. Wenn Ihre benutzerdefinierte Hilfsroutine oder Hookroutinen Gleitkommatypen verwenden, müssen sie den Gleitkommazustand auf Computern mit Registeraufrufkonventionen mit Gleitkommaparametern vollständig speichern und wiederherstellen. Seien Sie vorsichtig mit dem verzögerten Laden der CRT-DLL, wenn Sie CRT-Funktionen aufrufen, die Gleitkommaparameter in einem numerischen Datenprozessorstapel in der Hilfsfunktion annehmen.  
  
## <a name="see-also"></a>Siehe auch  
 [Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)   
 [LoadLibrary-Funktion](https://msdn.microsoft.com/library/windows/desktop/ms684175.aspx)   
 [GetModuleHandle-Funktion](https://msdn.microsoft.com/library/windows/desktop/ms683199.aspx)   
 [GetProcAddress-Funktion](https://msdn.microsoft.com/library/windows/desktop/ms683212.aspx)   
 [TlsAlloc-Funktion](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsalloc)   
 [TlsFree-Funktion](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsfree)   
 [TlsGetValue-Funktion](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue)   
 [TlsSetValue-Funktion](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlssetvalue)