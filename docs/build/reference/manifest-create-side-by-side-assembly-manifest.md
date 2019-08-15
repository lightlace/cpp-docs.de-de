---
title: /MANIFEST (Erstellen eines Manifests für eine parallele Assembly)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.GenerateManifest
helpviewer_keywords:
- -MANIFEST linker option
- /MANIFEST linker option
- MANIFEST linker option
ms.assetid: 98c52e1e-712c-4f49-b149-4d0a3501b600
ms.openlocfilehash: ea58b43accdd854665fad3b70d7aecbc9eaa0f9e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492780"
---
# <a name="manifest-create-side-by-side-assembly-manifest"></a>/MANIFEST (Erstellen eines Manifests für eine parallele Assembly)

```
/MANIFEST[:{EMBED[,ID=#]|NO}]
```

## <a name="remarks"></a>Hinweise

/MANIFEST gibt an, dass der Linker eine parallele Manifestdatei erstellen soll. Weitere Informationen zu Manifest-Dateien finden Sie unter [Manifest-Dateireferenz](/windows/win32/SbsCs/manifest-files-reference).

Die Standardeinstellung ist "/MANIFEST".

Die /MANIFEST:EMBED-Option gibt an, dass der Linker die Manifestdatei im Image als Ressource vom Typ "RT_MANIFEST" einbetten soll. Der optionale `ID`-Parameter ist die Ressourcen-ID, die für das Manifest verwendet werden soll. Verwenden Sie den Wert 1 für eine ausführbare Datei. Verwenden Sie den Wert 2 für eine DLL, damit diese private Abhängigkeiten angeben kann. Wenn der `ID`-Parameter nicht angegeben wird, ist der Standardwert 2, wenn die /DLL-Option festgelegt wird; andernfalls ist der Standardwert 1.

Ab Visual Studio 2008 enthalten Manifest-Dateien für ausführbare Dateien einen Abschnitt, in dem Informationen zur Benutzerkontensteuerung (User Account Control, UAC) angegeben werden. Wenn Sie/Manifest angeben, aber weder [/MANIFESTUAC](manifestuac-embeds-uac-information-in-manifest.md) noch [/dll](dll-build-a-dll.md), wird ein Standardmäßiges UAC-Fragment, bei dem die UAC-Ebene auf *asInvoker* festgelegt ist, in das Manifest eingefügt. Weitere Informationen zu UAC-Ebenen finden Sie unter [/MANIFESTUAC (bettet UAC-Informationen in Manifest ein)](manifestuac-embeds-uac-information-in-manifest.md).

Um das UAC-Standardverhalten zu ändern, führen Sie einen der folgenden Schritte aus:

- Geben Sie die /MANIFESTUAC-Option an, und legen Sie die UAC-Ebene auf den gewünschten Wert fest.

- Oder geben Sie die /MANIFESTUAC:NO-Option an, wenn Sie im Manifest kein UAC-Fragment generieren möchten.

Wenn Sie/Manifest nicht angeben, aber [/MANIFESTDEPENDENCY](manifestdependency-specify-manifest-dependencies.md) -Kommentare angeben, wird eine Manifest-Datei erstellt. Wenn Sie "/MANIFEST:NO" angeben, wird keine Manifestdatei erstellt.

Wenn Sie "/MANIFEST" angeben, wird der Name der Manifestdatei aus dem Namen der Ausgabedatei und der Endung .MANIFEST zusammengesetzt. Wenn die Ausgabedatei beispielsweise "MyFile.exe" heißt, hat die Manifestdatei den Namen "MyFile.exe.manifest".  Wenn Sie/MANIFESTFILE:*Name*angeben, ist der Name des Manifests der Name, den Sie in *Name*angeben.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Erweitern Sie den Knoten **Konfigurationseigenschaften**.

1. Erweitern Sie den Knoten **Linker**.

1. Wählen Sie die Eigenschaften Seite **Manifest-Datei** aus.

1. Ändern Sie die Eigenschaft **Manifest generieren** .

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateManifest%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
