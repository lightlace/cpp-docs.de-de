---
title: Compiler-Fehler C3610 | Microsoft-Dokumentation
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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 31cef33981bbc2063bf68e433f9d3ba32780363d
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3610"></a>Compilerfehler C3610
'Valuetype': Werttyp muss geschachtelt werden, bevor die Methode "Methode" aufgerufen werden kann  
  
 Standardmäßig ist ein Werttyp nicht auf dem verwalteten Heap. Bevor Sie Methoden aus .NET Runtime-Klassen, z. B. aufrufen können `Object`, müssen Sie den Werttyp auf den verwalteten Heap verschieben.  
  
 C3610 ist nur mit der veralteten-Compileroption erreichbar **/CLR: oldSyntax**.  

