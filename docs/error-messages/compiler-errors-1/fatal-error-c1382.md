---
title: "Schwerwiegender Fehler C1382 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1382"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1382"
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Schwerwiegender Fehler C1382
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die PCH\-Datei 'Datei' wurde neu erstellt, seitdem 'Objekt' generiert wurde.Erstellen Sie dieses Objekt neu  
  
 Der Compiler hat bei Verwendung von [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md) eine PCH\-Datei gefunden, die aktueller als eine CIL\-OBJ\-Datei ist, die auf diese Datei verweist.  Die Informationen in der CIL\-OBJ\-Datei sind veraltet.  Erstellen Sie das Objekt neu.  
  
 C1382 kann auch auftreten, wenn mit **\/Yc** kompiliert wird und trotzdem mehrere Quellcodedateien an den Compiler übergeben werden.  Um das Problem zu beheben, verwenden Sie **\/Yc** nicht, wenn mehrere Quellcodedateien an den Compiler übergeben werden.  Weitere Informationen finden Sie unter [\/Yc \(Datei der vorkompilierten Header erstellen\)](../../build/reference/yc-create-precompiled-header-file.md).