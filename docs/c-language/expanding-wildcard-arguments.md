---
title: "Erweitern von Platzhalterargumenten"
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
  - "C"
helpviewer_keywords: 
  - "Sternchen-Platzhalter"
  - "Erweitern von Platzhalterargumenten"
  - "Fragezeichen, Platzhalter"
  - "Platzhalter, Erweitern"
ms.assetid: 80a11c4b-0199-420e-a342-cf1d803be5bc
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Erweitern von Platzhalterargumenten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Wenn Sie ein C\-Programm ausführen, können Sie einen von zwei Platzhaltern – das Fragezeichen \(?\) und das Sternchen \(\*\) – verwenden, um Dateinamen\- und Pfadargumente in der Befehlszeile anzugeben.  
  
 Standardmäßig werden Platzhalter in Befehlszeilenargumenten nicht erweitert. Sie können den die normale `argv`\-Laderoutine für den Argumentvektor durch eine Version ersetzen, die Platzhalter durch eine Verknüpfung mit der Datei „setargv.obj“ oder der Datei „wsetargv.obj“ erweitert. Wenn das Programm eine `main`\-Funktion verwendet, stellen Sie eine Verknüpfung mit „setargv.obj“ her. Wenn das Programm eine `wmain`\-Funktion verwendet, stellen Sie eine Verknüpfung mit „wsetargv.obj“ her. Beide weisen das gleiche Verhalten auf.  
  
 Um eine Verknüpfung mit „setargv.obj“ oder „wsetargv.obj“ herzustellen, verwenden Sie die **\/link**\-Option. Zum Beispiel:  
  
 **cl example.c \/link setargv.obj**  
  
 Die Platzhalter werden auf dieselbe Weise wie Betriebssystembefehle erweitert. \(Weitere Informationen erhalten Sie im Benutzerhandbuch des Betriebssystems, wenn Sie mit Platzhaltern nicht vertraut sind.\)  
  
 **Ende Microsoft\-spezifisch**  
  
## Siehe auch  
 [Linkoptionen](../c-runtime-library/link-options.md)   
 [main\-Funktion und Programmausführung](../c-language/main-function-and-program-execution.md)