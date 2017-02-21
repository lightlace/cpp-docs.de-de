---
title: "LIBRARY | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LIBRARY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LIBRARY-Anweisung in .def-Dateien"
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# LIBRARY
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit dieser Anweisung wird LINK angewiesen, eine DLL zu erstellen.  Gleichzeitig erstellt **LINK** eine Importbibliothek, es sei denn, bei der Erstellung wird eine EXP\-Datei verwendet.  
  
```  
LIBRARY [library][BASE=address]  
```  
  
## Hinweise  
 Das *library*\-Argument gibt den internen Namen der DLL an.  Sie können auch die [\/OUT](../../build/reference/out-output-file-name.md)\-Linkeroption verwenden, um den Ausgabenamen für die DLL festzulegen.  
  
 Das BASE\=*address*\-Argument legt die Basisadresse fest, die das Betriebssystem zum Laden der DLL verwendet.  Durch dieses Argument wird 0x10000000, die Standardadresse für DLLs, überschrieben.  Einzelheiten über Basisadressen finden Sie in der Beschreibung der [\/BASE](../../build/reference/base-base-address.md)\-Option.  
  
 Achten Sie beim Erstellen einer DLL darauf, die [\/DLL](../../build/reference/dll-build-a-dll.md)\-Linkeroption zu verwenden.  
  
## Siehe auch  
 [Regeln für Moduldefinitionsanweisungen](../../build/reference/rules-for-module-definition-statements.md)