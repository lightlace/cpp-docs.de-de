---
title: 'Ressourcencompiler: Warnung RC4093 | Microsoft-Dokumentation'
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
ms.openlocfilehash: 9b1ca04b17ebdb9d48bc94032482caf48ad4aa00
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111562"
---
# <a name="resource-compiler-warning-rc4093"></a>Ressourcencompiler: Warnung RC4093

ohne Escapezeichen Zeilenumbruch innerhalb einer Zeichenkonstante im inaktiven code

Der Konstante Ausdruck, der eine `#if`, `#elif`, **#ifdef**, oder **#ifndef** Präprozessordirektive ergab 0 (null), und des Codes, dass inaktive folgt. Innerhalb des inaktiven Codes wurde Sie ein neue Zeilenumbruchzeichen in einer Gruppe von einfachen oder doppelten Anführungszeichen angezeigt.

Der gesamte Text, bis das doppelte Anführungszeichen innerhalb einer Zeichenkonstante betrachtet wurde.