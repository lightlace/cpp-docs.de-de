---
title: Befehlszeilenwarnung D9043 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: D9043
dev_langs: C++
helpviewer_keywords: D9043
ms.assetid: 9263e28d-217b-414c-bfb6-86efd3c27a77
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a8986926db2c32d9ae5ca73517c74ae9625e6bf5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="command-line-warning-d9043"></a>Befehlszeilenwarnung D9043
Es wurde ein ungültiger Wert 'Warning_level' für 'Compiler_option'; Wenn '4999'; Codeanalysewarnungen sind nicht mit Warnstufen verknüpft.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C9043 generiert.  
  
```  
// D9043.cpp  
// compile with: /analyze /w16001  
// D9043 warning expected  
int main() {}  
```