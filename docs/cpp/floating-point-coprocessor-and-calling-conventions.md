---
title: Gleitkomma-Coprozessor und Aufrufkonventionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- floating-point numbers [C++]
- floating-point coprocessor
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 66ccd54c4abb1d8d9761d5ded88beba76bfae043
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39401353"
---
# <a name="floating-point-coprocessor-and-calling-conventions"></a>Gleitkomma-Coprozessor und Aufrufkonventionen
Wenn Sie Assemblyroutinen für den zeigen Coprozessor Assembly schreiben sind, müssen Sie beibehalten, die floating-Steuerwort zeigen und den koprozessorstapel bereinigen, es sei denn, die Sie zurückgeben möchten eine **"float"** oder **doppelte** Wert (der die Funktion in St(0) zurückgeben sollte.  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufkonventionen](../cpp/calling-conventions.md)