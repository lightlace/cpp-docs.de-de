---
title: 'Ressourcencompiler: Warnung RC4093 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RC4093
dev_langs: C++
helpviewer_keywords: RC4093
ms.assetid: 3c61b4a4-b418-465b-a4fd-cb1ff0adb8dd
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4d21cbba379e72675b8957be58dc712b83673947
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-warning-rc4093"></a>Ressourcencompiler: Warnung RC4093
ohne Escapezeichen Zeilenvorschubzeichen in Zeichenkonstante in inaktiver code  
  
 Der Konstante Ausdruck eine `#if`, `#elif`, **#ifdef**, oder **#ifndef** Präprozessordirektive ausgewertet, um 0 (null), dem Code vorgenommen werden, folgt inaktiv. Innerhalb dieser inaktiver Code wurden ein neue Zeilenumbruchzeichen in einer Gruppe von einfache oder doppelte Anführungszeichen ein.  
  
 Gesamten Text, bis das doppelte Anführungszeichen innerhalb einer Zeichenkonstante betrachtet wurde.