---
title: Gleitkomma-Coprozessor und Aufrufkonventionen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- floating-point numbers [C++]
- floating-point coprocessor
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0d16e5c99dc96618bc8657fbd7d3025f9dd410dc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="floating-point-coprocessor-and-calling-conventions"></a>Gleitkomma-Coprozessor und Aufrufkonventionen
Wenn Sie Assemblyroutinen für den Fließkomma-Koprozessor Assembly schreiben sind, Sie müssen beibehalten fließkommasteuerwort und den koprozessorstapel bereinigen, es sei denn, die Sie zurückgeben einer **"float"** oder **doppelte** Wert (die die Funktion in St(0) zurückgeben sollte.  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufkonventionen](../cpp/calling-conventions.md)