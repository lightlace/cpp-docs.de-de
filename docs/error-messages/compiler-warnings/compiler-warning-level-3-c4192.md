---
title: Compilerwarnung (Stufe 3) C4192 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4192
dev_langs:
- C++
helpviewer_keywords:
- C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3bae9b7af95de94b8f667cb09710af21044f8b80
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33291413"
---
# <a name="compiler-warning-level-3-c4192"></a>Compilerwarnung (Stufe 3) C4192
automatisch beim Importieren einer Typbibliothek "Library" ausgeschlossen "Name"  
  
 Ein `#import` Bibliothek enthält ein Element *Namen*, d. h. auch in den Headern der Win32-System definiert. Aufgrund der Einschränkungen von Typbibliotheken, z. B. Namen **IUnknown** oder GUID häufig definiert sind in einer Typbibliothek, die Definition der Systemheadern duplizieren. `#import` Diese Elemente erkennt, und lehnen sie in den Headerdateien TLH und TLI integrieren.  
  
 Um dieses Verhalten zu überschreiben, verwenden `#import` Attribute [No_auto_exclude](../../preprocessor/no-auto-exclude.md) und [include()](../../preprocessor/include-parens.md).