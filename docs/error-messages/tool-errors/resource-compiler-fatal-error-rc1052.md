---
title: 'Ressourcencompiler: Schwerwiegender Fehler RC1052'
ms.date: 11/04/2016
f1_keywords:
- RC1052
helpviewer_keywords:
- RC1052
ms.assetid: 59803673-492b-44fa-80fa-df93b8aaf9fb
ms.openlocfilehash: 2ab9dd48420ca263abbf3da22da878a3e74a2151
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62297293"
---
# <a name="resource-compiler-fatal-error-rc1052"></a>Ressourcencompiler: Schwerwiegender Fehler RC1052

Compilerlimit: zu tiefe Schachtelung von #if- oder #ifdef-Blöcke

Die maximal zulässige Schachtelungstiefe für `#if`- und `#ifdef`-Anweisungen wird vom Programm überschritten.

Dieser Fehler kann durch Includedateien, die diese Präprozessordirektiven verwenden, verursacht werden.

Um dieses Problem zu beheben, verringern Sie die Anzahl der geschachtelten `#if`- und `#ifdef`-Anweisungen in der Ressourcendatei. Wenn das Problem durch Header-Dateien verursacht wird, die in der Ressourcendatei enthalten sind, verringern Sie die Anzahl der geschachtelten `#if` und `#ifdef`-Anweisungen in den Headerdateien. Wenn dies nicht möglich ist, sollten Sie eine neue Headerdatei in Ihrer Ressourcendatei mit dem Präprozessor auf vorhandenen eingeschlossenen Headerdateien erstellen und einschließen. Weitere Informationen finden Sie unter den [/p (Vorverarbeitung in eine Datei)](../../build/reference/p-preprocess-to-a-file.md) -Compileroption.