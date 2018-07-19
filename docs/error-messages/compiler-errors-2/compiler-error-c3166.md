---
title: Compilerfehler Fehler C3166 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3166
dev_langs:
- C++
helpviewer_keywords:
- C3166
ms.assetid: ec3e330d-c15d-4158-8268-09101486c566
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f1996da7bb937fd00a4283ad94a4885432a9d47a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33247705"
---
# <a name="compiler-error-c3166"></a>Compilerfehler Fehler C3166
"Zeiger": einen Zeiger auf einen internen __gc-Zeiger als Member von "Type" kann nicht deklariert werden  
  
Der Compiler hat eine ungültige Zeigerdeklaration gefunden (ein `__nogc` Zeiger auf eine `__gc` Zeiger.). 
  
C3166 ist nur über die veraltete Compileroption erreichbar **/CLR: oldSyntax**.  
