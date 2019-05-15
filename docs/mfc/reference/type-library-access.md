---
title: Zugreifen auf die Typbibliothek
ms.date: 11/04/2016
helpviewer_keywords:
- type libraries [MFC], accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
ms.openlocfilehash: 23d4675bd3638d2effd1b967f0729f9e70dac6de
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611534"
---
# <a name="type-library-access"></a>Zugreifen auf die Typbibliothek

Typbibliotheken verfügbar Schnittstellen, die der OLE-Steuerelements für andere OLE-fähigen Anwendungen. Jeder OLE-Steuerelements benötigen eine Typbibliothek aus, wenn eine oder mehrere Schnittstellen sind verfügbar gemacht werden.

Die folgenden Makros zulassen ein OLE-Steuerelements, um Zugriff auf eine eigene Typbibliothek bereitzustellen:

### <a name="type-library-access"></a>Zugreifen auf die Typbibliothek

|||
|-|-|
|[DECLARE_OLETYPELIB](#declare_oletypelib)|Deklariert eine `GetTypeLib` Memberfunktion eines OLE-Steuerelements (muss in der Klassendeklaration verwendet werden).|
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|Implementiert eine `GetTypeLib` Memberfunktion eines OLE-Steuerelements (muss in der klassenimplementierung verwendet werden).|

##  <a name="declare_oletypelib"></a>  DECLARE_OLETYPELIB

Deklariert die `GetTypeLib` Memberfunktion der Steuerelementklasse.

```
DECLARE_OLETYPELIB(class_name)
```

### <a name="parameters"></a>Parameter

*class_name*<br/>
Der Name des der Control-Klasse, die im Zusammenhang mit der Typbibliothek.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro in der Headerdatei des Steuerelement-Klasse.

### <a name="requirements"></a>Anforderungen

**Header:** afxdisp.h

##  <a name="implement_oletypelib"></a>  IMPLEMENT_OLETYPELIB

Das Steuerelement implementiert die `GetTypeLib` Member-Funktion.

```
IMPLEMENT_OLETYPELIB(class_name, tlid, wVerMajor,  wVerMinor)
```

### <a name="parameters"></a>Parameter

*class_name*<br/>
Der Name des der Control-Klasse, die im Zusammenhang mit der Typbibliothek.

*tlid*<br/>
Die ID der Typbibliothek.

*wVerMajor*<br/>
Die Typ-Bibliothek Hauptversionsnummer.

*wVerMinor*<br/>
Die Typ-Bibliothek Nebenversionsnummer.

### <a name="remarks"></a>Hinweise

Dieses Makro muss in der Implementierungsdatei für jede Steuerelementklasse angezeigt werden, die die DECLARE_OLETYPELIB-Makro verwendet.

### <a name="requirements"></a>Anforderungen

**Header:** afxdisp.h

## <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
