---
title: Compilerwarnung (Stufe 3) C4192 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4192
dev_langs:
- C++
helpviewer_keywords:
- C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 022c0e0aac8d231963ddf6d5d3715d55f726a8b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4192"></a>Compilerwarnung (Stufe 3) C4192
automatisch beim Importieren einer Typbibliothek "Library" ausgeschlossen "Name"  
  
 Ein `#import` Bibliothek enthält ein Element *Namen*, d. h. auch in den Headern der Win32-System definiert. Aufgrund der Einschränkungen von Typbibliotheken, z. B. Namen **IUnknown** oder GUID häufig definiert sind in einer Typbibliothek, die Definition der Systemheadern duplizieren. `#import`Diese Elemente erkennt, und lehnen sie in den Headerdateien TLH und TLI integrieren.  
  
 Um dieses Verhalten zu überschreiben, verwenden `#import` Attribute [No_auto_exclude](../../preprocessor/no-auto-exclude.md) und [include()](../../preprocessor/include-parens.md).