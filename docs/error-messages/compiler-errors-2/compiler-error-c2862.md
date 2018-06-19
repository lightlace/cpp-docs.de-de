---
title: Compilerfehler C2862 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2862
dev_langs:
- C++
helpviewer_keywords:
- C2862
ms.assetid: c04d8499-b799-48a1-9fb4-7902a0b0ac8e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb9aac4a7c4bd43dcd4f0e688c955619133d375f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33247514"
---
# <a name="compiler-error-c2862"></a>Compilerfehler C2862
'Schnittstelle': eine Schnittstelle kann nur öffentliche Member besitzen  
  
 Geschützte und Private Member nur von anderen Memberfunktionen zugegriffen werden kann. Solche Member sind keine Use in einer Schnittstelle aus, da er Implementierungen für eines ihrer Elemente nicht bereitstellen kann.  
  
 Im folgenden Beispiel wird C2862 generiert:  
  
```  
// C2862.cpp  
// compile with: /c  
#include <unknwn.h>  
  
[object, uuid="60719E20-EF37-11D1-978D-0000F805D73B"]  
__interface IMyInterface {  
   HRESULT mf1(void);   // OK  
protected:  
   HRESULT mf2(int *b);   // C2862  
private:  
   HRESULT mf3(int *c);   // C2862  
};  
```