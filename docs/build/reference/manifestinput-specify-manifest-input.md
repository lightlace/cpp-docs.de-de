---
title: /MANIFESTINPUT (Angeben einer Manifesteingabedatei)
ms.date: 11/04/2016
ms.assetid: a0b0c21e-1f9b-4d8c-bb3f-178f57fa7f1b
ms.openlocfilehash: bf192664a7a2402b06621167d91dff67ce0741a9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62321357"
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

Diese Option kann nicht direkt in Visual Studio festgelegt werden. Verwenden Sie stattdessen die **zusätzliche Manifestdateien** -Eigenschaft des Projekts an zusätzliche Manifestdateien einschließen. Weitere Informationen finden Sie unter [Eingabe und Ausgabe, Manifesttool, Konfigurationseigenschaften, \<Projectname > Property Pages Dialog Box](input-and-output-manifest-tool.md).

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
