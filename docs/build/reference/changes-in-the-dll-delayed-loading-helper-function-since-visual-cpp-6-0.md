---
title: "&#196;nderungen an der Hilfsfunktion f&#252;r das verz&#246;gerte Laden von DLLs seit Visual&#160;C++ 6.0"
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
  - "__delayLoadHelper2-Funktion"
  - "Verzögertes Laden von DLLs, Neues"
  - "Hilfsfunktionen, Neues"
  - "PFromRva-Methode"
ms.assetid: 99f0be69-105d-49ba-8dd5-3be7939c0c72
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# &#196;nderungen an der Hilfsfunktion f&#252;r das verz&#246;gerte Laden von DLLs seit Visual&#160;C++ 6.0
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn verschiedene Versionen von Visual C\+\+ auf dem Computer verwendet werden oder wenn eine eigene Hilfsfunktion definiert wird, können die an der Hilfsfunktion für verzögertes Laden von DLLs vorgenommenen Änderungen Auswirkungen aufweisen.  Beispiel:  
  
-   **\_\_delayLoadHelper** ist jetzt **\_\_delayLoadHelper2**  
  
-   **\_\_pfnDliNotifyHook** ist jetzt **\_\_pfnDliNotifyHook2**  
  
-   **\_\_pfnDliFailureHook** ist jetzt **\_\_pfnDliFailureHook2**  
  
-   **\_\_FUnloadDelayLoadedDLL** ist jetzt **\_\_FUnloadDelayLoadedDLL2**  
  
> [!NOTE]
>  Wenn die Standardhilfsfunktion verwendet wird, werden sich die Änderungen nicht auswirken.  Es sind keine Änderungen beim Aufruf des Linkers zu berücksichtigen.  
  
## Mehrere Versionen von Visual C\+\+  
 Stellen Sie sicher, dass der Linker delayimp.lib entspricht, wenn Sie verschiedene Versionen von Visual C\+\+ auf dem Computer verwenden.  Ist das nicht der Fall, wird ein Linkerfehler auftreten, der darüber informiert, dass es sich entweder bei `___delayLoadHelper2@8` oder `___delayLoadHelper@8` um ein nicht aufgelöstes externes Symbol handelt.  Die erste Meldung bedeutet, dass Sie einen neuen Linker mit einer alten Version von **delayimp.lib** verwenden. Die zweite Meldung bedeutet, dass Sie einen alten Linker mit einer neuen Version von **delayimp.lib** verwenden.  
  
 Tritt ein nicht aufgelöster Linkerfehler auf, führen Sie [dumpbin \/linkermember](../../build/reference/linkermember.md):1 für die Datei delayimp.lib aus, die die Hilfsfunktion erwartungsgemäß enthält. Auf diese Weise ermitteln Sie, welche Hilfsfunktion stattdessen definiert wurde.  Die Hilfsfunktion kann auch in einer Objektdatei definiert sein. Rufen Sie [dumpbin \/symbols](../../build/reference/symbols.md) auf, und suchen Sie nach `delayLoadHelper(2)`.  
  
 Wenn Sie den Linker von Visual C\+\+ 6.0 verwenden, gehen Sie folgendermaßen vor:  
  
-   Führen Sie **dumpbin** für die LIB\-Datei oder die OBJ\-Datei der Hilfsfunktion für verzögertes Laden aus, um festzustellen, ob **\_\_delayLoadHelper2** in ihr definiert wird.  Wenn nicht, tritt beim Verknüpfen ein Fehler auf.  
  
-   Definieren Sie **\_\_delayLoadHelper** in der LIB\-Datei oder der OBJ\-Datei der Hilfsfunktion für verzögertes Laden.  
  
## Benutzerdefinierte Hilfsfunktion  
 Wenn Sie eine eigene Hilfsfunktion definiert haben und die aktuelle Version von Visual C\+\+ verwenden, gehen Sie folgendermaßen vor:  
  
-   Benennen Sie die Hilfsfunktion in **\_\_delayLoadHelper2** um.  
  
-   Da die Zeiger im Verzögerungsdeskriptor \(**ImgDelayDescr** in **delayimp.h**\) von absoluten Adressen \(VAs\) zu relativen Adressen \(RVAs\) geändert wurden, um sowohl in 32\-Bit\-Programmen als auch in 64\-Bit\-Programmen erwartungsgemäß zu funktionieren, müssen Sie diese in Zeiger zurückkonvertieren.  Eine neue Funktion, PFromRva, wurde eingeführt und ist in delayhlp.cpp enthalten.  Sie können diese Funktion für jedes der Felder im Deskriptor verwenden, um es entweder in 32\-Bit\- oder 64\-Bit\-Zeiger zu konvertieren.  Die Standardhilfsfunktion für verzögertes Laden stellt weiterhin eine gute Vorlage dar, um sie als Beispiel zu verwenden.  
  
## Laden aller Importe für eine verzögert geladene DLL  
 Der Linker kann alle Importe aus einer DLL laden, die als verzögert geladen festgelegt wurde.  Weitere Informationen finden Sie unter [Laden aller Importe für eine verzögert geladene DLL](../../build/reference/loading-all-imports-for-a-delay-loaded-dll.md).  
  
## Siehe auch  
 [Understanding the Helper Function](assetId:///6279c12c-d908-4967-b0b3-cabfc3e91d3d)