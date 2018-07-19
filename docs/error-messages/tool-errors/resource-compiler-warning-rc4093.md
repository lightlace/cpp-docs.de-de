---
title: 'Ressourcencompiler: Warnung RC4093 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC4093
dev_langs:
- C++
helpviewer_keywords:
- RC4093
ms.assetid: 3c61b4a4-b418-465b-a4fd-cb1ff0adb8dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9cca3c2a139e1109746f3a690cfb3f31509a9fe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322431"
---
# <a name="resource-compiler-warning-rc4093"></a>Ressourcencompiler: Warnung RC4093
ohne Escapezeichen Zeilenvorschubzeichen in Zeichenkonstante in inaktiver code  
  
 Der Konstante Ausdruck eine `#if`, `#elif`, **#ifdef**, oder **#ifndef** Präprozessordirektive ausgewertet, um 0 (null), dem Code vorgenommen werden, folgt inaktiv. Innerhalb dieser inaktiver Code wurden ein neue Zeilenumbruchzeichen in einer Gruppe von einfache oder doppelte Anführungszeichen ein.  
  
 Gesamten Text, bis das doppelte Anführungszeichen innerhalb einer Zeichenkonstante betrachtet wurde.