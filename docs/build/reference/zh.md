---
title: /ZH (Hash Algorithmus für die Berechnung der Datei Prüf Summe in Debuginformationen)
description: Verwenden Sie die/ZH-Compileroption, um MD5-, SHA-1-oder SHA-256-Quelldatei Prüfsummen in Debuginformationen zu aktivieren.
ms.date: 09/16/2019
f1_keywords:
- /ZH
- /ZH:MD5
- /ZH:SHA1
- /ZH:SHA_256
helpviewer_keywords:
- /ZH
- /ZH:MD5
- /ZH:SHA1
- /ZH:SHA_256
- /ZH compiler option
- /ZH:MD5 compiler option
- /ZH:SHA1 compiler option
- /ZH:SHA_256 compiler option
- Hash algorithm for file checksum in debug info
ms.openlocfilehash: f05dc2bc3b8ce4502ff16a6e19fdbb10763b34ba
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2019
ms.locfileid: "71686935"
---
# <a name="zh-hash-algorithm-for-calculation-of-file-checksum-in-debug-info"></a>/ZH (Hash Algorithmus für die Berechnung der Datei Prüf Summe in Debuginformationen)

Gibt an, welcher Kryptografische Hash Algorithmus zum Generieren einer Prüfsumme für jede Quelldatei verwendet werden soll.

## <a name="syntax"></a>Syntax

> **/ZH:** {**MD5**|**SHA1**|**SHA_256**}

## <a name="arguments"></a>Argumente

**/ZH: MD5**\
Verwenden Sie einen MD5-Hash für die Prüfsumme. Diese Option ist die Standardeinstellung.

**/ZH: SHA1**-\
Verwenden Sie einen SHA-1-Hash für die Prüfsumme.

**/ZH: SHA_256**\
Verwenden Sie einen SHA-256-Hash für die Prüfsumme.

## <a name="remarks"></a>Hinweise

PDB-Dateien speichern eine Prüfsumme für jede Quelldatei, die in den Objektcode der zugehörigen ausführbaren Datei kompiliert wird. Die Prüfsumme ermöglicht dem Debugger, zu überprüfen, ob der zu ladende Quellcode mit der ausführbaren Datei übereinstimmt. Der Compiler und der Debugger unterstützen die Hash Algorithmen MD5, SHA-1 und SHA-256. Standardmäßig verwendet der Compiler einen MD5-Hash, um die Prüfsumme zu generieren. Sie können diese Option explizit mithilfe der **/ZH: MD5** -Option angeben.

Aufgrund der Gefahr von Kollisions Problemen in MD5 und SHA-1 empfiehlt Microsoft die Verwendung der Option **/ZH: SHA_256** . Der SHA-256-Hash kann zu einer geringfügigen Zunahme der Kompilierungszeiten führen.

Wenn mehr als eine **/ZH** -Option angegeben ist, wird die letzte Option verwendet.

Die **/ZH** -Option ist ab Visual Studio 2019, Version 16,4, verfügbar.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Legen Sie die Dropdown- **Konfiguration** auf **alle Konfigurationen**fest.

1. Klicken Sie auf der Eigenschaftenseite auf **Konfigurationseigenschaften** > **C/C++**  > **Befehlszeile**.

1. Ändern Sie die Eigenschaft **zusätzliche Optionen** , um eine **/ZH: MD5**-, **/ZH: SHA1**-oder **/ZH: SHA_256** -Option hinzuzufügen, und wählen Sie dann **OK**aus.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](compiler-options.md)\
[Quell Server](/windows/win32/debug/source-server-and-source-indexing)
