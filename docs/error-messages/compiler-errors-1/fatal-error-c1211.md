---
title: Schwerwiegender Fehler C1211 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1211
dev_langs: C++
helpviewer_keywords: C1211
ms.assetid: df0ca70d-ec6e-4400-926a-b877e2599978
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a57418d53626aefa1b9616b2790bd23e0a2d941e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1211"></a>Schwerwiegender Fehler C1211
Das benutzerdefinierte TypeForwardedTo-Attribut wird von der installierten Laufzeitversion nicht unterstützt.  
  
 C1211 tritt auf, wenn Sie einen Compiler der aktuellen Version, aber eine Common Language Runtime (CLR) einer früheren Version verwenden.  
  
 Bestimmte Funktionen des Compilers funktionieren möglicherweise nicht in einer früheren Version der Laufzeit.  
  
 Installieren Sie die CLR, die im Lieferumfang des von Ihnen verwendeten Compilers enthalten war, um C1211 zu beheben.  
  
 Weitere Informationen finden Sie unter [Typweiterleitung (C + c++ / CLI)](../../windows/type-forwarding-cpp-cli.md).