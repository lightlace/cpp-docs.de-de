---
title: 'Ressourcencompiler: Warnung RW4004 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RW4004
dev_langs: C++
helpviewer_keywords: RW4004
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0249f7d01ee344f0fa17bdc39e58e9fce26c9b25
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-warning-rw4004"></a>Ressourcencompiler: Warnung RW4004
ASCII-Zeichen entspricht nicht dem virtuellem Tastencode  
  
 Für den virtueller Tastencode in einer VIRTKEY-Zugriffstaste wurde ein Zeichenfolgenliteral verwendet.  
  
 Trotz der Warnung können Sie den Vorgang fortsetzen. Sie informiert Sie jedoch darüber, dass die generierten Zugriffstasten möglicherweise nicht mit der Zeichenfolge übereinstimmen, die Sie angegeben haben. (VIRTKEY-Zugriffstasten verwenden andere Tastencodes als ASCII-Zugriffstasten.)  
  
 Obwohl Zeichenfolgenliterale syntaktisch zulässig sind, können Sie nur sicherstellen, dass Sie die Zugriffstaste sollen erhalten, mit der **VK_\* #define** Werte in Windows.h dar.