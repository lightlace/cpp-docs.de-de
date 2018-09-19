---
title: 'Ressourcencompiler: Schwerwiegender Fehler RC1018 | Microsoft-Dokumentation'
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
ms.openlocfilehash: c2c4fa0a9964c3faeed010b82f8cd98f2782fb1a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028505"
---
# <a name="resource-compiler-fatal-error-rc1018"></a>Ressourcencompiler: Schwerwiegender Fehler RC1018

Unerwartetes "#elif"

Die `#elif` Richtlinie nicht angezeigt, in eine `#if`, **#ifdef**, oder **#ifndef** zu erstellen.

Stellen Sie sicher, dass ein `#if`, **#ifdef**, oder **#ifndef** -Anweisung vor dieser Anweisung in Kraft.