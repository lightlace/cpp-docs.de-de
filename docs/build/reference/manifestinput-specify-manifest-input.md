---
title: /MANIFESTINPUT (Angeben einer Manifesteingabedatei)
ms.date: 11/04/2016
ms.assetid: a0b0c21e-1f9b-4d8c-bb3f-178f57fa7f1b
ms.openlocfilehash: f0b60b1f9ebff4547017fcfac586f00625311937
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57418807"
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

Die **/MANIFESTINPUT** Option gibt den Pfad der Eingabedatei für das eingebettete Manifest in ein ausführbares Image zu erstellen. Wenn Sie mehrere Manifesteingabedateien haben, verwenden Sie den Schalter mehrfach, einmal für jede Eingabedatei. Die Manifesteingabedateien werden zusammengeführt, um das eingebettete Manifest zu erstellen. Diese Option erfordert die **/MANIFEST: EINBETTEN von** Option.

Diese Option kann nicht direkt in Visual Studio festgelegt werden. Verwenden Sie stattdessen die **zusätzliche Manifestdateien** -Eigenschaft des Projekts an zusätzliche Manifestdateien einschließen. Weitere Informationen finden Sie unter [Eingabe und Ausgabe, Manifesttool, Konfigurationseigenschaften, \<Projectname > Property Pages Dialog Box](../../ide/input-and-output-manifest-tool.md).

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)
