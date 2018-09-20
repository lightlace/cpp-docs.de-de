---
title: Geben Sie Zugriff auf die Medienbibliothek | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- type libraries [MFC], accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1a361c1e50945b19562082424c178a21191bd0b9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404736"
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

*CLASS_NAME*<br/>
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

*CLASS_NAME*<br/>
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
