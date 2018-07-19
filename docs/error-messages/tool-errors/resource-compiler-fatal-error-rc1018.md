---
title: 'Ressourcencompiler: Schwerwiegender Fehler RC1018 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC1018
dev_langs:
- C++
helpviewer_keywords:
- RC1018
ms.assetid: bb1d2efd-6898-412f-bb03-9ff94c54e4dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc54586d03aaf84882120cee0428990caa8cae97
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33339851"
---
# <a name="resource-compiler-fatal-error-rc1018"></a>Ressourcencompiler: Schwerwiegender Fehler RC1018
Unerwartetes "#elif"  
  
 Die `#elif` Richtlinie ist nicht vorhanden, innerhalb einer `#if`, **#ifdef**, oder **#ifndef** erstellen.  
  
 Stellen Sie sicher, dass es ist ein `#if`, **#ifdef**, oder **#ifndef** Anweisung ausführt, bevor diese Anweisung wirksam.