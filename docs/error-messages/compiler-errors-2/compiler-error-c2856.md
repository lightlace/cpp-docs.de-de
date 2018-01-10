---
title: Compilerfehler C2856 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2856
dev_langs: C++
helpviewer_keywords: C2856
ms.assetid: fe616c51-124e-49e3-9dd8-883ec1660680
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ab5fdd09fbbd7c6b1f213404dfbf6d9d9e5612ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2856"></a>Compilerfehler C2856
\#Pragma-Hdrstop darf nicht innerhalb eines #if-Blocks sein.  
  
 Die `hdrstop` Pragma kann nicht innerhalb des Hauptteils eines Blocks für die bedingte Kompilierung platziert werden.  
  
 Verschieben der `#pragma hdrstop` Anweisung, um einen Bereich, der nicht in enthalten ist ein `#if/#endif` Block.