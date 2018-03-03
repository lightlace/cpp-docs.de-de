---
title: 'Ressourcencompiler: Schwerwiegender Fehler RC1018 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC1018
dev_langs:
- C++
helpviewer_keywords:
- RC1018
ms.assetid: bb1d2efd-6898-412f-bb03-9ff94c54e4dc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cbae052efa85c5ee17517363e7a5f38475dbc37e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-fatal-error-rc1018"></a>Ressourcencompiler: Schwerwiegender Fehler RC1018
Unerwartetes "#elif"  
  
 Die `#elif` Richtlinie ist nicht vorhanden, innerhalb einer `#if`, **#ifdef**, oder **#ifndef** erstellen.  
  
 Stellen Sie sicher, dass es ist ein `#if`, **#ifdef**, oder **#ifndef** Anweisung ausführt, bevor diese Anweisung wirksam.