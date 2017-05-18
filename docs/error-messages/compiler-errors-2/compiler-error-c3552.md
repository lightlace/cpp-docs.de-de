---
title: Compilerfehler C3552 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3552
dev_langs:
- C++
helpviewer_keywords:
- C3552
ms.assetid: 83401524-1bf1-44c0-8aca-a6eb35c4224c
caps.latest.revision: 4
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
ms.openlocfilehash: ae268ae3c0d7857aa2c2cbafe9e158656f657f1a
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3552"></a>Compilerfehler C3552
"Typname": Ein spät angegebener Rückgabetyp darf nicht "auto" enthalten.  
  
 Wenn Sie das `auto` -Schlüsselwort als Platzhalter für den Rückgabetyp einer Funktion verwenden, müssen Sie einen spät angegebenen Rückgabetyp angeben. Allerdings können Sie kein weiteres `auto` -Schlüsselwort verwenden, um den spät angegebenen Rückgabetyp anzugeben. Im folgenden Codefragment wird beispielsweise der Fehler C3552 verursacht.  
  
 `auto myFunction->auto; // C3552`
