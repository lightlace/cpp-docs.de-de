---
title: /MANIFESTINPUT (Angeben einer Manifesteingabedatei)
ms.date: 07/24/2019
ms.assetid: a0b0c21e-1f9b-4d8c-bb3f-178f57fa7f1b
ms.openlocfilehash: 7b7bd54f98003d9158276fcf75fd61ffb5348585
ms.sourcegitcommit: 720b74dddb1cdf4e570d55103158304ee1df81f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2019
ms.locfileid: "68606461"
---
# <a name="manifestinput-specify-manifest-input"></a>/MANIFESTINPUT (Angeben einer Manifesteingabedatei)

Gibt eine Manifesteingabedatei an, die dem Manifest hinzugefügt wird, das im Image eingebettet ist.

## <a name="syntax"></a>Syntax

```
/MANIFESTINPUT:filename
```

### <a name="parameters"></a>Parameter

*filename*<br/>
Die Manifestdatei, die dem eingebetteten Manifest hinzuzufügen ist.

## <a name="remarks"></a>Hinweise

Die **/MANIFESTINPUT** -Option gibt den Pfad einer Eingabedatei an, die zum Erstellen des eingebetteten Manifests in einem ausführbaren Image verwendet werden soll. Wenn Sie mehrere Manifesteingabedateien haben, verwenden Sie den Schalter mehrfach, einmal für jede Eingabedatei. Die Manifesteingabedateien werden zusammengeführt, um das eingebettete Manifest zu erstellen. Diese Option erfordert die Option **/Manifest: Embed** .

Diese Option kann nicht direkt in Visual Studio festgelegt werden. Verwenden Sie stattdessen die Eigenschaft **zusätzliche Manifest-Dateien** des Projekts, um zusätzliche Manifest-Dateien anzugeben, die eingeschlossen werden sollen. Weitere Informationen finden Sie unter [Manifest-Tool-Eigenschaften Seiten](manifest-tool-property-pages.md).

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
