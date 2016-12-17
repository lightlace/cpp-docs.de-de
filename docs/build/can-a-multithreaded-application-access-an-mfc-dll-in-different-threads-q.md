---
title: "Kann eine Multithreadanwendung auf eine MFC-DLL in unterschiedlichen Threads zugreifen?"
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
  - "DLLs [C++], Multithreading"
  - "MFC-DLLs [C++], Multithreading"
  - "Multithreading [C++], DLLs"
  - "Threading [MFC], DLLs"
ms.assetid: e3452e62-021e-4d23-9cce-cff41eb8b46b
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Kann eine Multithreadanwendung auf eine MFC-DLL in unterschiedlichen Threads zugreifen?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Multithreadanwendungen können auf reguläre DLLs zugreifen, die dynamisch mit MFC\- und Erweiterungs\-DLLs aus unterschiedlichen Threads verknüpft sind.  Außerdem kann eine Anwendung ab Visual C\+\+, Version 4.2, auf reguläre DLLs zugreifen, die aus mehreren, in der Anwendung erstellten Threads heraus statisch mit MFC verknüpft sind.  
  
 Vor Version 4.2 konnte nur ein externer Thread an eine reguläre DLL angefügt werden, die statisch mit MFC verknüpft war.  Weitere Informationen über Einschränkungen beim Zugriff auf reguläre DLLs, die \(vor Visual C\+\+, Version 4.2\) aus mehreren Threads heraus statisch mit MFC verknüpft werden, finden Sie im Knowledge Base\-Artikel "Multiple Threads and MFC \_USRDLLs" \(Q122676, nur auf Englisch verfügbar\).  
  
 Beachten Sie, dass der Begriff "USRDLL" in der Visual C\+\+\-Dokumentation nicht mehr verwendet wird.  Eine reguläre DLL, die statisch mit MFC verknüpft ist, hat dieselben Merkmale wie die frühere USRDLL.  
  
## Siehe auch  
 [FAQ \(Häufig gestellte Fragen\) zu DLLs](../build/dll-frequently-asked-questions.md)