---
title: Compilerfehler C3610 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3610
dev_langs:
- C++
helpviewer_keywords:
- C3610
ms.assetid: 9349a348-9d37-4a00-9eab-481039268d31
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0cacac87535864c6268d0f078566b9ab224e9151
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3610"></a>Compilerfehler C3610
"Valuetype": Werttyp muss geschachtelt werden, bevor die Methode 'Methode' aufgerufen werden kann  
  
 Standardmäßig ist ein Werttyp nicht auf dem verwalteten Heap. Bevor Sie Methoden aus .NET Common Language Runtime-Klassen, z. B. aufrufen können `Object`, müssen Sie den Werttyp auf den verwalteten Heap zu verschieben.  
  
 C3610 ist nur über die veraltete Compileroption erreichbar **/CLR: oldSyntax**.  

