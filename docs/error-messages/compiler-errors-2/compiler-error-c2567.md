---
title: "Compilerfehler C2567"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2567"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2567"
ms.assetid: 9c140ac9-7059-47e6-9ba1-e7939c8c0dc3
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2567
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Metadaten in 'Datei' können nicht geöffnet werden. Die Datei wurde möglicherweise gelöscht oder verschoben.  
  
 Eine Metadatendatei, auf die im Quellcode verwiesen wird \(mit `#using`\) befindet sich während der Ausführung des Compiler\-Back\-End\-Prozesses nicht in demselben Verzeichnis, in dem sie sich während der Ausführung des Compiler\-Front\-End\-Prozesses befand.  Weitere Informationen finden Sie unter [\#using\-Direktive](../../preprocessor/hash-using-directive-cpp.md).  
  
 C2567 wird unter Umständen ausgegeben, wenn Sie auf einem Computer mit **\/c** kompilieren und anschließend versuchen, auf einem anderen Computer eine Codegenerierung während der Verknüpfung durchzuführen.  Weitere Informationen finden Sie unter [\/LTCG \(Code zur Verknüpfungszeit generieren\)](../../build/reference/ltcg-link-time-code-generation.md).  
  
 Der Fehler weist möglicherweise auch darauf hin, dass der Computer über keinen freien Arbeitsspeicher mehr verfügt.  
  
 Um diesen Fehler zu vermeiden, vergewissern Sie sich, dass die Metadatendatei während des gesamten Buildprozesses an demselben Speicherort verbleibt.