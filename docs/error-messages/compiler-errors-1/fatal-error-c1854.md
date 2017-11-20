---
title: Schwerwiegender Fehler C1854 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1854
dev_langs: C++
helpviewer_keywords: C1854
ms.assetid: 8c21a9cc-1737-475c-9e57-8725cd8937c1
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d35a3aae8f52f28e8775e09d23355e931420bfee
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1854"></a>Schwerwiegender Fehler C1854
  
> Informationen, die beim Anlegen der vorkompilierten Headerdatei in der Objektdatei kann nicht überschrieben werden: "*Filename*"  
  
Die Sie angegeben haben die [/Yu (vorkompilierte Headerdatei verwenden)](../../build/reference/yu-use-precompiled-header-file.md) Option nach dem Angeben der [/Yc (Datei der vorkompilierten Header erstellen)](../../build/reference/yc-create-precompiled-header-file.md) Option für dieselbe Datei.  
  
Um dieses Problem zu beheben, legen Sie im Allgemeinen nur eine Datei im Projekt mit kompiliert werden die **"/ Yc"** aus, und legen Sie alle anderen Dateien, die bei der Kompilierung der **"/ Yu"** Option. Weitere Informationen zur Verwendung von der **"/ Yc"** Option, und wie sie in der Visual Studio-IDE fest, finden Sie unter [/Yc (Datei der vorkompilierten Header erstellen)](../../build/reference/yc-create-precompiled-header-file.md). Weitere Informationen zum Verwenden von vorkompilierter Headers finden Sie unter [Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md).  
