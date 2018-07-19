---
title: Schwerwiegender Fehler C1005 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1005
dev_langs:
- C++
helpviewer_keywords:
- C1005
ms.assetid: 150daf8e-a38a-4669-9c1a-a05b5a1f65ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 13ff7f5dbc1f9ecb66c54f52fae4a38d1e4d4664
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33197714"
---
# <a name="fatal-error-c1005"></a>Schwerwiegender Fehler C1005
Zeichenfolge zu lang für Puffer  
  
 Eine Zeichenfolge in einer Zwischendatei des Compilers hat zu einem Pufferüberlauf geführt.  
  
 Sie erhalten diesen Fehler möglicherweise, wenn der an die Compileroptionen [/Fd](../../build/reference/fd-program-database-file-name.md) oder [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) übergebene Parameter größer als 256 Bytes ist.