---
title: Schwerwiegender Fehler C1383 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1383
dev_langs:
- C++
helpviewer_keywords:
- C1383
ms.assetid: ca224d14-d687-4fd6-80c2-8b82f28924ea
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: bbd890a7506059f939ca6d8957f71e20cba771f8
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1383"></a>Schwerwiegender Fehler C1383
Die Compileroption /GL ist nicht mit der installierten Version der Common Language Runtime kompatibel.  
  
 C1383 tritt auf, wenn Sie eine frühere Version der Common Language Runtime mit einem neueren Compiler verwenden und bei der Kompilierung **/clr** und **/GL.**verwenden.  
  
 Verwenden Sie entweder nicht **/GL** mit **/clr** , oder installieren Sie die im Lieferumfang des Compilers enthaltene Version der Common Language Runtime.  
  
 Weitere Informationen finden Sie unter [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md) und [/GL (Optimierung des ganzen Programms)](../../build/reference/gl-whole-program-optimization.md).
