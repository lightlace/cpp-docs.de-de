---
title: Compilerwarnung (Stufe 1) C4276 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4276
dev_langs:
- C++
helpviewer_keywords:
- C4276
ms.assetid: 9d738c2d-29e5-408a-b9ff-be1a850b2238
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: afedab27c2fb93075aa33053c12ec6973824f144
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4276"></a>Compilerwarnung (Stufe 1) C4276
'Funktion': kein Prototyp bereitgestellt wird. davon ausgegangen, dass keine Parameter  
  
 Wenn Sie die Adresse einer Funktion mit ergreifen der [__stdcall](../../cpp/stdcall.md) -Aufrufkonvention, geben Sie einen Prototyp, damit der Compiler den ergänzten Namen der Funktion erstellen kann. Da *Funktion* keinen Prototyp der Compiler für die Erstellung der ergänzte Name besitzt, die Funktion hat keine Parameter annimmt.