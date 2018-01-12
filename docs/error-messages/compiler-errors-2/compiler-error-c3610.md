---
title: Compilerfehler C3610 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3610
dev_langs: C++
helpviewer_keywords: C3610
ms.assetid: 9349a348-9d37-4a00-9eab-481039268d31
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 33fba9e64a6d314d503a42d0cf5512a2edb9c3a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3610"></a>Compilerfehler C3610
"Valuetype": Werttyp muss geschachtelt werden, bevor die Methode 'Methode' aufgerufen werden kann  
  
 Standardmäßig ist ein Werttyp nicht auf dem verwalteten Heap. Bevor Sie Methoden aus .NET Common Language Runtime-Klassen, z. B. aufrufen können `Object`, müssen Sie den Werttyp auf den verwalteten Heap zu verschieben.  
  
 C3610 ist nur über die veraltete Compileroption erreichbar **/CLR: oldSyntax**.  
