---
title: Compilerwarnung (Stufe 3) C4192 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4192
dev_langs: C++
helpviewer_keywords: C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ff07a7fd5af7c9e4d73d9a4ce679edc7ab5e6b43
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4192"></a>Compilerwarnung (Stufe 3) C4192
automatisch beim Importieren einer Typbibliothek "Library" ausgeschlossen "Name"  
  
 Ein `#import` Bibliothek enthält ein Element *Namen*, d. h. auch in den Headern der Win32-System definiert. Aufgrund der Einschränkungen von Typbibliotheken, z. B. Namen **IUnknown** oder GUID häufig definiert sind in einer Typbibliothek, die Definition der Systemheadern duplizieren. `#import`Diese Elemente erkennt, und lehnen sie in den Headerdateien TLH und TLI integrieren.  
  
 Um dieses Verhalten zu überschreiben, verwenden `#import` Attribute [No_auto_exclude](../../preprocessor/no-auto-exclude.md) und [include()](../../preprocessor/include-parens.md).