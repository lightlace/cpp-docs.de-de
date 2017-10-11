---
title: bad_function_call-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- functional/std::bad_function_call
dev_langs:
- C++
helpviewer_keywords:
- bad_function_call class
ms.assetid: b70a0268-43ff-4f3b-a283-faf1cb172d4c
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: c6aa47c6eb3d9fc39eed6b68856641cd86d27ba5
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="badfunctioncall-class"></a>bad_function_call-Klasse
Meldet einen ungültigen Funktionsaufruf.  
  
## <a name="syntax"></a>Syntax  
  
```  
class bad_function_call  
 : public std::exception {  
 };  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Klasse beschreibt eine Ausnahme, die ausgelöst wurde, um anzugeben, dass ein Aufruf von `operator()` in einer [function-Klasse](../standard-library/function-class.md) durchgeführt wurde.

