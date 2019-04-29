---
title: Klassenfabriken und Lizenzierung
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros.classes
helpviewer_keywords:
- class factories [MFC], and licensing
ms.assetid: 53c4856a-4062-46db-9f69-dd4339f746b3
ms.openlocfilehash: 3788d904bf903481d57dd73a28bf6eafadd5f019
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392556"
---
# <a name="class-factories-and-licensing"></a>Klassenfabriken und Lizenzierung

Um eine Instanz des OLE-Steuerelements zu erstellen, ruft eine Container-Anwendung auf eine Memberfunktion der Klassenfactory des Steuerelements. Da das Steuerelement ein tatsächliches OLE-Objekt ist, ist die Klassenfactory für die Erstellung von Instanzen Ihres Steuerelements verantwortlich. Jede Steuerelementklasse OLE benötigen eine Klassenfactory.

Ein weiteres wichtiges Feature der OLE-Steuerelemente ist ihre Fähigkeit, eine Lizenz zu erzwingen. Assistent ermöglicht Ihnen während der Erstellung der Steuerelementprojekt Lizenzierung zu integrieren. Weitere Informationen zu Lizenzierung, finden Sie im Artikel [ActiveX-Steuerelemente: Lizenzieren eines ActiveX-Steuerelements](../../mfc/mfc-activex-controls-licensing-an-activex-control.md).

Die folgende Tabelle enthält einige Makros und Funktionen, die zum Deklarieren und Implementieren Ihres Steuerelements Klassenfactory und Lizenz des Steuerelements.

### <a name="class-factories-and-licensing"></a>Klassenfabriken und Lizenzierung

|||
|-|-|
|[DECLARE_OLECREATE_EX](#declare_olecreate_ex)|Deklariert die Klassenfactory für eine OLE-Steuerelements oder einer Eigenschaft die Seite an.|
|[IMPLEMENT_OLECREATE_EX](#implement_olecreate_ex)|Das Steuerelement implementiert die `GetClassID` Funktion, und eine Instanz der Klassenfactory deklariert.|
|[BEGIN_OLEFACTORY](#begin_olefactory)|Beginnt die Deklaration der Lizenzierung Funktionen an.|
|[END_OLEFACTORY](#end_olefactory)|Beendet die Deklaration der Lizenzierung Funktionen an.|
|[AfxVerifyLicFile](#afxverifylicfile)|Überprüft, ob ein Steuerelement für die Verwendung auf einem bestimmten Computer lizenziert ist.|

##  <a name="declare_olecreate_ex"></a>  DECLARE_OLECREATE_EX

Deklariert eine Klassenfactory und `GetClassID` Memberfunktion der Steuerelementklasse.

```
DECLARE_OLECREATE_EX(class_name)
```

### <a name="parameters"></a>Parameter

*class_name*<br/>
Der Name der Steuerelement-Klasse.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro in der Headerdatei des Steuerelement-Klasse für ein Steuerelement, das keine Lizenzierung unterstützt.

Beachten Sie, dass dieses Makro den gleichen Zweck wie im folgenden Beispiel dient:

[!code-cpp[NVC_MFCAxCtl#14](../../mfc/reference/codesnippet/cpp/class-factories-and-licensing_1.h)]

### <a name="requirements"></a>Anforderungen

  **Header** afxctl.h

##  <a name="implement_olecreate_ex"></a>  IMPLEMENT_OLECREATE_EX

Implementiert die Klassenfactory des Steuerelements und dem [GetClassID](../../mfc/reference/colecontrol-class.md#getclassid) Memberfunktion der Steuerelementklasse.

```
IMPLEMENT_OLECREATE_EX(
   class_name,
    external_name,
    l,
    w1,
    w2,
    b1,
    b2,
    b3,
    b4,
    b5,
    b6,
    b7,
    b8)
```

### <a name="parameters"></a>Parameter

*class_name*<br/>
Der Name des Steuerelements Eigenschaftenseitenklasse.

*external_name*<br/>
Der Objektname, der für Anwendungen verfügbar gemacht wird.

*l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8*<br/>
Komponenten von der Klasse CLSID. Weitere Informationen zu diesen Parametern finden Sie unter den Hinweisen zu [IMPLEMENT_OLECREATE](run-time-object-model-services.md#implement_olecreate).

### <a name="remarks"></a>Hinweise

Dieses Makro muss in der Implementierungsdatei für jede Steuerelementklasse angezeigt werden, die die DECLARE_OLECREATE_EX-Makro oder die BEGIN_OLEFACTORY und END_OLEFACTORY-Makros verwendet. Der externe Name ist der Bezeichner des OLE-Steuerelements, die für andere Anwendungen verfügbar gemacht wird. Container verwenden diesen Namen, um ein Objekt dieser Klasse Control anzufordern.

### <a name="requirements"></a>Anforderungen

  **Header** afxctl.h

##  <a name="begin_olefactory"></a>  BEGIN_OLEFACTORY

Beginnt die Deklaration der Klassenfactory in der Headerdatei der Steuerelementklasse.

```
BEGIN_OLEFACTORY(class_name)
```

### <a name="parameters"></a>Parameter

*class_name*<br/>
Gibt den Namen der Steuerelement-Klasse, deren Klassenfactory, dies ist.

### <a name="remarks"></a>Hinweise

Deklarationen von Funktionen Lizenzierung Klassenfactory sollte unmittelbar nach BEGIN_OLEFACTORY beginnen.

### <a name="requirements"></a>Anforderungen

  **Header** afxctl.h

##  <a name="end_olefactory"></a>  END_OLEFACTORY

Beendet die Deklaration der Klassenfactory des Steuerelements an.

```
END_OLEFACTORY(class_name)
```

### <a name="parameters"></a>Parameter

*class_name*<br/>
Der Name der Steuerelement-Klasse, deren Klassenfactory, dies ist.

### <a name="requirements"></a>Anforderungen

  **Header** afxctl.h

##  <a name="afxverifylicfile"></a>  AfxVerifyLicFile

Rufen Sie diese Funktion, um sicherzustellen, dass die Lizenzdatei durch den Namen `pszLicFileName` gilt für die OLE-Steuerelements.

```
BOOL AFXAPI AfxVerifyLicFile(
    HINSTANCE  hInstance,
    LPCTSTR  pszLicFileName,
    LPOLESTR  pszLicFileContents,
    UINT cch = -1);
```

### <a name="parameters"></a>Parameter

*hInstance*<br/>
Der Instanzhandle, der DLL an, das lizenzierte Steuerelement zugeordnet werden soll.

*pszLicFileName*<br/>
Verweist auf eine Null-terminierte Zeichenfolge, die die Lizenz-Dateinamen enthält.

*pszLicFileContents*<br/>
Verweist auf eine Bytesequenz, die die Sequenz finden Sie am Anfang der Lizenzdatei übereinstimmen muss.

*cch*<br/>
Anzahl der Zeichen in *PszLicFileContents*.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Lizenzdatei vorhanden und mit der Zeichensequenz in beginnt *PszLicFileContents*, andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn *Cch* -1 ist, diese Funktion verwendet:

[!code-cpp[NVC_MFC_Utilities#36](../../mfc/codesnippet/cpp/class-factories-and-licensing_2.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** afxctl.h

## <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
