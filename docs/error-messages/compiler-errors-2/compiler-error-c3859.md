---
title: Compilerfehler C3859 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3859
dev_langs: C++
helpviewer_keywords: C3859
ms.assetid: 40e93b25-4393-4467-90de-035434a665c7
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8a132eb7dbf09421ad5c99249b0208e5f901156b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3859"></a>Compilerfehler C3859
Virtueller Speicherbereich für PCH wurde überschritten; kompilieren Sie erneut mit einer Befehlszeilenoption von -Zmvalue oder größer  
  
 Ihr vorkompilierter Header ist zu klein für die Menge an Daten, die der Compiler versucht einzufügen. Verwenden der **/Zm** Compilerflag einen größeren Wert für die vorkompilierte Headerdatei anzugeben. Weitere Informationen finden Sie unter [/Zm (Geben Sie vorkompilierte Header Speicherbelegung)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).