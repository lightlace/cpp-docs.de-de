---
title: / DEFAULTLIB (Standardbibliothek festlegen) | Microsoft Docs
ms.custom: ''
ms.date: 05/29/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.DefaultLibraries
- /defaultlib
dev_langs:
- C++
helpviewer_keywords:
- -DEFAULTLIB linker option
- DEFAULTLIB linker option
- /DEFAULTLIB linker option
- libraries, adding to list of
ms.assetid: 6af7ff49-c170-4a13-97e2-2b9ae2de20c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9afcaa0e229ec34ba91b4d60a7a4fa9acec2d7e3
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2018
ms.locfileid: "34569780"
---
# <a name="defaultlib-specify-default-library"></a>/DEFAULTLIB (Standardbibliothek festlegen)

Geben Sie eine Standardbibliothek an, zum Auflösen externer Verweise durchsucht.

## <a name="syntax"></a>Syntax

> **/ DEFAULTLIB**:_Bibliothek_

### <a name="arguments"></a>Argumente

|Argument|Beschreibung|
|-|-|
*Bibliothek*|Der Name einer Bibliothek beim Auflösen externer Verweise durchsucht.

## <a name="remarks"></a>Hinweise

Die **Option** Option Fügt eine *Bibliothek* zur Liste der Bibliotheken, mit dem LINK, beim Auflösen von Verweisen gesucht. Eine Bibliothek mit angegebenen **Option** nach Bibliotheken, die explizit angegeben werden, in der Befehlszeile und vor Standardbibliotheken, die mit dem Namen in der OBJ-Dateien gesucht wird.

Wenn Sie ohne Argumente wird die [/NODEFAULTLIB (Bibliotheken ignorieren)](../../build/reference/nodefaultlib-ignore-libraries.md) Option überschreibt alle **Option**:*Bibliothek* Optionen. Die **/NODEFAULTLIB**:*Bibliothek* option überschreibt **Option**:*Bibliothek* bei dem *Bibliothek*Namen in beiden angegeben ist.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Befehlszeile** Eigenschaftenseite.

1. In **Zusatzoptionen**, geben Sie einen **Option**:*Bibliothek* Option für jede Bibliothek zu suchen. Wählen Sie **OK** zum Speichern der Änderungen.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

- [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)
- [Linkeroptionen](../../build/reference/linker-options.md)
