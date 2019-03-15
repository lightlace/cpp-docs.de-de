---
title: / CETCOMPAT (ablaufsteuerung Erzwingungstechnologie kompatibel)
ms.date: 02/19/2019
f1_keywords:
- /CETCOMPAT
helpviewer_keywords:
- /CETCOMPAT linker option
- /CETCOMPAT
ms.openlocfilehash: 1a01dd45667f64dbcbe11acaf1180835bd0d6e31
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809846"
---
# <a name="cetcompat-control-flow-enforcement-technology-compatible"></a>/ CETCOMPAT (ablaufsteuerung Erzwingungstechnologie kompatibel)

Gibt an, ob ein ausführbares Image als kompatibel mit der ablaufsteuerung Erzwingung Technologie (MEZ) zu kennzeichnen.

## <a name="syntax"></a>Syntax

> **/CETCOMPAT**\[**:NO**]

## <a name="arguments"></a>Argumente

**NO**<br/>
Gibt an, dass die ausführbare Datei nicht mit MEZ kompatibel gekennzeichnet werden soll.

## <a name="remarks"></a>Hinweise

Ablaufsteuerung Erzwingung Technologie (MEZ) ist ein Computer-Prozessor-Feature, das zur Verteidigung gegen bestimmte Arten von Angriffen durch Schadsoftware bietet. Weitere Informationen finden Sie unter [Intel ablaufsteuerung Erzwingung Technology Preview](https://software.intel.com/sites/default/files/managed/4d/2a/control-flow-enforcement-technology-preview.pdf).

Die **/CETCOMPAT** Linkeroption weist den Linker an die Binärwerte als MEZ kompatible zu markieren. **/CETCOMPAT:No** die Binärdatei als nicht kompatibel mit der Uhr CET markiert. Wenn beide Optionen in der Befehlszeile angegeben werden, wird die letzte angegeben verwendet. Dieser Schalter ist derzeit nur für X86- und X64 Architekturen.

Die **/CETCOMPAT** Option ist verfügbar ab der im Toolset Visual Studio 2019 Vorschau 3.

### <a name="to-set-the-cetcompat-linker-option-in-visual-studio"></a>So legen Sie die /CETCOMPAT-Linkeroption in Visual Studio fest

1. Öffnen der **Eigenschaftenseiten** im Dialogfeld für das Projekt. Weitere Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Befehlszeile** Eigenschaftenseite.

1. In der **zusätzliche Optionen** fügen **/CETCOMPAT** oder **/CETCOMPAT:NO** und wählen Sie dann **OK** oder **übernehmen**zum Speichern der Änderungen.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

Diese Option ist keine programmgesteuerte Variante verfügbar sein.

## <a name="see-also"></a>Siehe auch

[Linkeroptionen](linker-options.md)
