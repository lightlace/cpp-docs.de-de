---
title: Linkertoolfehler Lnk1223 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1223
dev_langs: C++
helpviewer_keywords: LNK1223
ms.assetid: c4728c36-daee-462f-a1c7-8733dcdec88e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 41d3de1080fd6b1cc3e8fbc5ca948482229f306e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1223"></a>Linkertoolfehler LNK1223
Ungültige oder beschädigte Datei: Datei enthält unzulässige .pdata-Beiträge  
  
 Bei RISC-Plattformen, die Pdata verwenden, wird dieser Fehler auftreten, wenn der Compiler einen .pdata-Abschnitt mit unsortierten Einträgen ausgegeben hat.  
  
 Um dieses Problem zu beheben, kompilieren Sie ohne [/GL (Optimierung des ganzen Programms)](../../error-messages/tool-errors/linker-tools-error-lnk1223.md) aktiviert. Leere Funktionsbodys können in einigen Fällen diesen Fehler auch verursacht.