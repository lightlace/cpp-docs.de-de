---
title: Tasks.vs.json-Schemareferenz (C++)
ms.date: 02/11/2019
helpviewer_keywords:
- Open Folder Projects in Visual C++
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
ms.openlocfilehash: d0f62f6cddf3701da391880532bd2f554cc19130
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315052"
---
# <a name="tasksvsjson-c"></a>Tasks.vs.json (C++)

Eine `tasks.vs.json`-Datei kann zu einem „Ordner öffnen“-Projekt hinzugefügt werden, um einen beliebigen Task zu definieren und diesen dann über das Kontextmenü des **Projektmappen-Explorers** aufzurufen. CMake-Projekte verwenden diese Datei in der Regel nicht, da alle Buildbefehle in `CMakeLists.txt` angegeben sind. Bei anderen Buildsystemen als CMake können Sie hier Ihre Buildbefehle angeben und Buildskripts aufrufen. Allgemeine Informationen zur Verwendung von „tasks.vs.json“ finden Sie unter [Anpassen von Build- und Debugtasks für die Open Folder-Entwicklung](/visualstudio/ide/customize-build-and-debug-tasks-in-visual-studio).

