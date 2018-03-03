---
title: Compilerwarnung (Stufe 1) C4276 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4276
dev_langs:
- C++
helpviewer_keywords:
- C4276
ms.assetid: 9d738c2d-29e5-408a-b9ff-be1a850b2238
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: af9a32da86a0ea9e530af03a2175976d4cd9f091
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4276"></a>Compilerwarnung (Stufe 1) C4276
'Funktion': kein Prototyp bereitgestellt wird. davon ausgegangen, dass keine Parameter  
  
 Wenn Sie die Adresse einer Funktion mit ergreifen der [__stdcall](../../cpp/stdcall.md) -Aufrufkonvention, geben Sie einen Prototyp, damit der Compiler den ergänzten Namen der Funktion erstellen kann. Da *Funktion* keinen Prototyp der Compiler für die Erstellung der ergänzte Name besitzt, die Funktion hat keine Parameter annimmt.