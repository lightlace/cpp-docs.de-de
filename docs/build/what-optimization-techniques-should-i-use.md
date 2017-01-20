---
title: "Welche Optimierungstechniken sollten verwendet werden, um die Leistung der Clientanwendung beim Laden zu verbessern?"
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
  - "DLLs [C++], Optimieren"
  - "Optimierung [C++], DLLs"
  - "Leistung [C++], DLLs"
ms.assetid: 2f8bbfb5-08b9-4a35-8302-25a1966881b1
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Welche Optimierungstechniken sollten verwendet werden, um die Leistung der Clientanwendung beim Laden zu verbessern?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Ihre DLL eine reguläre, statisch mit MFC verknüpfte DLL ist, können Sie die Dateigröße verringern, indem Sie die DLL in eine reguläre DLL ändern, die dynamisch mit MFC verknüpft wird.  
  
 Wenn die DLL über eine große Anzahl exportierter Funktionen verfügt, verwenden Sie \(anstelle von **\_\_declspec\(dllexport\)**\) eine DEF\-Datei, um die Funktionen zu exportieren. Führen Sie für jede exportierte Funktion das [NONAME\-Attribut](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md) der DEF\-Datei aus.  Dieses Attribut führt dazu, dass nur der Ordinalwert und nicht der Funktionsname in der Exporttabelle der DLL gespeichert wird, wodurch die Dateigröße verringert wird.  
  
 Implizit mit einer Anwendung verknüpfte DLLs werden zusammen mit der Anwendung geladen.  Um die Geschwindigkeit beim Laden zu verbessern, versuchen Sie, die DLL in mehrere DLLs aufzuteilen.  Legen Sie alle Funktionen, die von der aufrufenden Anwendung unmittelbar nach dem Laden benötigt werden, in einer DLL ab, und konfigurieren Sie die aufrufende Anwendung so, dass sie implizit mit dieser DLL verknüpft wird.  Speichern Sie die anderen Funktionen, die von der aufrufenden Anwendung nicht sofort benötigt werden, in einer anderen DLL, und konfigurieren Sie die Anwendung so, dass sie explizit mit dieser DLL verknüpft wird.  Weitere Informationen finden Sie unter [Bestimmen der geeigneten Verknüpfungsmethode](../build/determining-which-linking-method-to-use.md).  
  
## Siehe auch  
 [FAQ \(Häufig gestellte Fragen\) zu DLLs](../build/dll-frequently-asked-questions.md)