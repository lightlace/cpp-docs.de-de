---
title: Compilerfehler C3453 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3453
dev_langs:
- C++
helpviewer_keywords:
- C3453
ms.assetid: dbefdbcf-f697-4239-b7a5-1d99b85e9e7f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3f21a5833c618c5a5dfcc9ff2b608c5ec15bd1aa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33257034"
---
# <a name="compiler-error-c3453"></a>Compilerfehler C3453
'attribut': Das Attribut wurde nicht angewendet, da der Qualifizierer 'assembly' nicht übereinstimmte.  
  
 Attribute auf Assembly- oder Modulebene können nur als eigenständige Anweisungen angegeben werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3453 generiert:  
  
```  
// C3453.cpp  
// compile with: /clr /c  
[assembly:System::CLSCompliant(true)]   // C3453  
// try the following line instead  
// [assembly:System::CLSCompliant(true)];  
ref class X {};  
```