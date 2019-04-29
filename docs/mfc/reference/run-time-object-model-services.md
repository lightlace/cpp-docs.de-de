---
title: Objektmodelldienste zur Laufzeit
ms.date: 03/27/2019
f1_keywords:
- vc.mfc.macros
helpviewer_keywords:
- run-time object model services macros
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
ms.openlocfilehash: 59f5be1d8bb38295b50732583fea47924160cecf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310031"
---
# <a name="run-time-object-model-services"></a>Objektmodelldienste zur Laufzeit

Die Klassen [CObject](../../mfc/reference/cobject-class.md) und [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) mehrere Objektdienste, einschließlich des Zugriffs auf die Laufzeit Klasseninformationen, Serialisierung und dynamische objekterstellung zu kapseln. Alle Klassen abgeleitet `CObject` erben diese Funktionalität.

Zugriff auf die Laufzeit Klasseninformationen können Sie Informationen über die Klasse eines Objekts zur Laufzeit zu ermitteln. Die Möglichkeit, die die Klasse eines Objekts zur Laufzeit zu bestimmen ist nützlich, wenn es sich bei benötigten zusätzlichen typüberprüfung von Funktionsargumenten und wenn Sie basierend auf der Klasse eines Objekts von speziellen Code schreiben müssen. Laufzeit Klasseninformationen wird direkt von der Programmiersprache C++ nicht unterstützt.

Serialisierung ist der Prozess des Schreibens oder Lesen von Inhalten eines Objekts, zu oder aus einer Datei. Sie können die Serialisierung verwenden, um Inhalt des Objekts zu speichern, auch nachdem die Anwendung beendet wird. Das Objekt kann dann aus der Datei gelesen werden, wenn die Anwendung neu gestartet wird. Solche Datenobjekte werden als "dauerhaft".

Dynamische objekterstellung können Sie ein Objekt einer bestimmten Klasse zur Laufzeit zu erstellen. Beispielsweise müssen Dokument, Ansicht und dem Keyframe-Objekte die dynamische Erstellung unterstützen, da das Framework diese dynamisch erstellen muss.

Die folgende Tabelle enthält die MFC-Makros, die die Laufzeit Klasseninformationen, Serialisierung und die dynamische Erstellung unterstützen.

Weitere Informationen zu diesen objektmodelldienste zur Laufzeit Dienste sowie die Serialisierung finden Sie im Artikel [CObject-Klasse: Zugreifen auf Laufzeit-Klasseninformationen](../../mfc/accessing-run-time-class-information.md).

### <a name="run-time-object-model-services-macros"></a>Laufzeit-Objektmodell Services-Makros

|||
|-|-|
|[DECLARE_DYNAMIC](#declare_dynamic)|Ermöglicht den Zugriff auf die Laufzeit-Klasseninformationen (muss in der Klassendeklaration verwendet werden).|
|[DECLARE_DYNCREATE](#declare_dyncreate)|Ermöglicht die dynamische Erstellung und den Zugriff auf die Laufzeit-Klasseninformationen (muss in der Klassendeklaration verwendet werden).|
|[DECLARE_SERIAL](#declare_serial)|Ermöglicht die Serialisierung und den Zugriff auf die Laufzeit-Klasseninformationen (muss in der Klassendeklaration verwendet werden).|
|[IMPLEMENT_DYNAMIC](#implement_dynamic)|Ermöglicht den Zugriff auf die Laufzeit-Klasseninformationen (muss in der klassenimplementierung verwendet werden).|
|[IMPLEMENT_DYNCREATE](#implement_dyncreate)|Ermöglicht die dynamische Erstellung und den Zugriff auf die Laufzeitinformationen (muss in der klassenimplementierung verwendet werden).|
|[IMPLEMENT_SERIAL](#implement_serial)|Ermöglicht die Serialisierung und den Zugriff auf die Laufzeit-Klasseninformationen (muss in der klassenimplementierung verwendet werden).|
|[RUNTIME_CLASS](#runtime_class)|Gibt die `CRuntimeClass` -Struktur, die von der benannten Klasse entspricht.|

OLE erfordert häufig die dynamische Erstellung von Objekten zur Laufzeit. Beispielsweise muss eine OLE-Server-Anwendung OLE-Elemente dynamisch in Reaktion auf eine Anforderung von einem Client erstellen können. Entsprechend muss ein Automatisierungsserver Elemente als Reaktion auf Anforderungen von Benutzeroberflächenautomatisierungs-Clients erstellen können.

Die Microsoft Foundation Class-Bibliothek stellt zwei Makros, die bestimmte an OLE bereit.

### <a name="dynamic-creation-of-ole-objects"></a>Dynamische Erstellung von OLE-Objekte

|||
|-|-|
|[AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)|Bestimmt, ob die allgemeine Steuerelemente-Bibliothek die angegebene API implementiert.|
|[AFX_COMCTL32_IF_EXISTS2](#afx_comctl32_if_exists2)|Bestimmt, ob die allgemeine Steuerelemente-Bibliothek die angegebene API implementiert.|
|[DECLARE_OLECREATE](#declare_olecreate)|Ermöglicht es Objekten, die über OLE-Automatisierung erstellt werden.|
|[DECLARE_OLECTLTYPE](#declare_olectltype)|Deklariert die `GetUserTypeNameID` und `GetMiscStatus` Memberfunktionen der Steuerelementklasse.|
|[DECLARE_PROPPAGEIDS](#declare_proppageids)|Deklariert, dass das OLE-Steuerelement, eine Liste der Eigenschaftenseiten bietet, um ihre Eigenschaften anzuzeigen.|
|[IMPLEMENT_OLECREATE](#implement_olecreate)|Ermöglicht es Objekten, die von der OLE-System erstellt werden.|
|[IMPLEMENT_OLECTLTYPE](#implement_olectltype)|Implementiert die `GetUserTypeNameID` und `GetMiscStatus` Memberfunktionen der Steuerelementklasse.|
|[IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags)|Entweder dieses Makro oder [IMPLEMENT_OLECREATE](#implement_olecreate) muss angezeigt werden, in der Implementierungsdatei für jede Klasse, die verwendet `DECLARE_OLECREATE`. |

## <a name="afx_comctl32_if_exists"></a> AFX_COMCTL32_IF_EXISTS

Bestimmt, ob die allgemeine Steuerelemente-Bibliothek die angegebene API implementiert.

### <a name="syntax"></a>Syntax

  ```
AFX_COMCTL32_IF_EXISTS(  proc );
```

### <a name="parameters"></a>Parameter

*proc*<br/>
Zeiger auf eine Null-terminierte Zeichenfolge, die den Namen der Funktion enthält oder der Funktion Ordinalwert angibt. Wenn dieser Parameter über einen Ordinalwert ist, muss es jedoch das niederwertige Wort sein. das höherwertige Wort muss 0 (null) sein. Dieser Parameter muss im Unicode-Format sein.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro, um zu bestimmen, ob die allgemeine Steuerelemente-Bibliothek die Funktion vom angegeben *Proc* (statt [GetProcAddress](/windows/desktop/api/libloaderapi/nf-libloaderapi-getprocaddress).

### <a name="requirements"></a>Anforderungen

afxcomctl32.h, afxcomctl32.inl

## <a name="afx_comctl32_if_exists2"></a>  AFX_COMCTL32_IF_EXISTS2

Bestimmt, ob die allgemeine Steuerelemente-Bibliothek die angegebene API implementiert (Dies ist die Unicode-Version von [AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)).

### <a name="syntax"></a>Syntax

```
AFX_COMCTL32_IF_EXISTS2( proc );
```

### <a name="parameters"></a>Parameter

*proc*<br/>
Zeiger auf eine Null-terminierte Zeichenfolge, die den Namen der Funktion enthält oder der Funktion Ordinalwert angibt. Wenn dieser Parameter über einen Ordinalwert ist, muss es jedoch das niederwertige Wort sein. das höherwertige Wort muss 0 (null) sein. Dieser Parameter muss im Unicode-Format sein.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro, um zu bestimmen, ob die allgemeine Steuerelemente-Bibliothek die Funktion vom angegeben *Proc* (statt [GetProcAddress](/windows/desktop/api/libloaderapi/nf-libloaderapi-getprocaddress). Dieses Makro ist die Unicode-Version von AFX_COMCTL32_IF_EXISTS.

### <a name="requirements"></a>Anforderungen

afxcomctl32.h, afxcomctl32.inl

##  <a name="declare_dynamic"></a>  DECLARE_DYNAMIC

Fügt die Fähigkeit zur Laufzeit Zugriff auf Informationen über die Klasse eines Objekts beim Ableiten einer Klasse von `CObject`.

```
DECLARE_DYNAMIC(class_name)
```

### <a name="parameters"></a>Parameter

*class_name*<br/>
Der tatsächliche Name der Klasse.

### <a name="remarks"></a>Hinweise

Fügen Sie die DECLARE_DYNAMIC-Makro die Headerdateien (h)-Modul für die Klasse hinzu und anschließend schließen Sie das Modul in alle cpp-Module, die Zugriff auf Objekte dieser Klasse benötigen.

Wenn Sie die dynamische DECLARE_ und IMPLEMENT_DYNAMIC-Makros verwenden, wie beschrieben, können Sie dann das RUNTIME_CLASS-Makro und die `CObject::IsKindOf` Funktion, um die Klasse der Objekte zur Laufzeit zu bestimmen.

Wenn in der Klassendeklaration DECLARE_DYNAMIC enthalten ist, muss in der klassenimplementierung IMPLEMENT_DYNAMIC enthalten sein.

Weitere Informationen zu den DECLARE_DYNAMIC-Makro, finden Sie unter [CObject-Klasse Themen](../../mfc/using-cobject.md).

### <a name="example"></a>Beispiel

Siehe das Beispiel für [IMPLEMENT_DYNAMIC](#implement_dynamic).

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="declare_dyncreate"></a>  DECLARE_DYNCREATE

Aktiviert die Objekte `CObject`-abgeleitete Klassen dynamisch zur Laufzeit erstellt werden.

```
DECLARE_DYNCREATE(class_name)
```

### <a name="parameters"></a>Parameter

*class_name*<br/>
Der tatsächliche Name der Klasse.

### <a name="remarks"></a>Hinweise

Das Framework verwendet diese Fähigkeit, um neue Objekte dynamisch zu erstellen. Zum Beispiel die neue Ansicht erstellt, wenn Sie ein neues Dokument zu öffnen. Dokument, Ansicht und dem Frameklassen sollte die dynamische Erstellung unterstützen, da das Framework diese dynamisch erstellen muss.

Fügen Sie das DECLARE_DYNCREATE-Makro in der h-Modul für die Klasse hinzu, und schließen Sie das Modul in alle cpp-Module, die Zugriff auf Objekte dieser Klasse benötigen.

Wenn in der Klassendeklaration DECLARE_DYNCREATE enthalten ist, muss in der klassenimplementierung IMPLEMENT_DYNCREATE enthalten sein.

Weitere Informationen zu den DECLARE_DYNCREATE-Makro, finden Sie unter [CObject-Klasse Themen](../../mfc/using-cobject.md).

> [!NOTE]
>  Das DECLARE_DYNCREATE-Makro enthält alle Funktionen der DECLARE_DYNAMIC.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [IMPLEMENT_DYNCREATE](#implement_dyncreate).

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

## <a name="declareolectltype"></a>DECLARE_OLECTLTYPE

Deklariert die `GetUserTypeNameID` und `GetMiscStatus` Memberfunktionen der Steuerelementklasse.

### <a name="syntax"></a>Syntax

```
DECLARE_OLECTLTYPE( class_name )
```

### <a name="parameters"></a>Parameter

*class_name*<br/>
Der Name der Steuerelement-Klasse.

### <a name="remarks"></a>Hinweise

`GetUserTypeNameID` und `GetMiscStatus` sind reine virtuelle Funktionen, die im deklarierten `COleControl`. Da diese Funktionen rein sind virtuell, sie müssen überschrieben werden in der Steuerelementklasse. Zusätzlich zu DECLARE_OLECTLTYPE müssen Sie Ihrer Klassendeklaration des Steuerelements die IMPLEMENT_OLECTLTYPE-Makro hinzufügen.

### <a name="requirements"></a>Anforderungen

**Header:** afxctl.h

## <a name="declareproppageids"></a>DECLARE_PROPPAGEIDS

Deklariert, dass das OLE-Steuerelement, eine Liste der Eigenschaftenseiten bietet, um ihre Eigenschaften anzuzeigen.

### <a name="syntax"></a>Syntax

```
DECLARE_PROPPAGEIDS( class_name )
```

### <a name="parameters"></a>Parameter

*class_name*<br/>
Der Name der Steuerelement-Klasse, die die Eigenschaftenseiten besitzt.

### <a name="remarks"></a>Hinweise

Verwenden der `DECLARE_PROPPAGEIDS` Makro am Ende der Klassendeklaration. Verwenden Sie dann in der CPP-Datei, die die Member-Funktionen für die Klasse definiert die `BEGIN_PROPPAGEIDS` Makro, Makroeinträge für die einzelnen Seiten des Steuerelements, und die `END_PROPPAGEIDS` Makro, um das Ende der Liste der Seite zu deklarieren.

Weitere Informationen zu Eigenschaftenseiten, finden Sie im Artikel [ActiveX-Steuerelemente: Eigenschaftenseiten](../mfc-activex-controls-property-pages.md).

### <a name="requirements"></a>Anforderungen

**Header:** afxctl.h

##  <a name="declare_serial"></a>  DECLARE_SERIAL

Generiert den Code der C++-Header für eine `CObject`-abgeleitete Klasse, die serialisiert werden kann.

```
DECLARE_SERIAL(class_name)
```

### <a name="parameters"></a>Parameter

*class_name*<br/>
Der tatsächliche Name der Klasse.

### <a name="remarks"></a>Hinweise

Serialisierung ist der Prozess der Schreib- und Lesezugriffe auf den Inhalt eines Objekts in und aus einer Datei.

Verwenden Sie das DECLARE_SERIAL-Makro in einem h-Modul, und klicken Sie dann enthalten Sie das Modul in alle cpp-Modulen, die Zugriff auf Objekte dieser Klasse.

Wenn in der Klassendeklaration DECLARE_SERIAL enthalten ist, muss in der klassenimplementierung IMPLEMENT_SERIAL enthalten sein.

Die DECLARE_SERIAL-Makro enthält alle Funktionen der DECLARE_DYNAMIC und DECLARE_DYNCREATE.

Können Sie das Makro AFX_API automatisch exportieren die `CArchive` Extraktionsoperator für Klassen, die DECLARE_SERIAL und IMPLEMENT_SERIAL-Makros zu verwenden. Zuordnen von Klammern Sie die Klassendeklarationen (befindet sich in der h-Datei) mit dem folgenden Code:

[!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]

Weitere Informationen zu den DECLARE_SERIAL-Makro, finden Sie unter [CObject-Klasse Themen](../../mfc/using-cobject.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCObjectSample#21](../../mfc/codesnippet/cpp/run-time-object-model-services_2.h)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="implement_dynamic"></a>  IMPLEMENT_DYNAMIC

Generiert den C++-Code für eine dynamische `CObject`-Klasse mit der Run-Time-Zugriff auf den Klassennamen und die Position innerhalb der Hierarchie.

```
IMPLEMENT_DYNAMIC(class_name, base_class_name)
```

### <a name="parameters"></a>Parameter

*class_name*<br/>
Der tatsächliche Name der Klasse.

*base_class_name*<br/>
Der Name der Basisklasse.

### <a name="remarks"></a>Hinweise

Verwenden Sie das IMPLEMENT_DYNAMIC-Makro in einem cpp-Modul, und klicken Sie dann verknüpfen Sie den resultierende Objektcode nur einmal zu.

Weitere Informationen finden Sie unter [CObject-Klasse Themen](../../mfc/using-cobject.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCObjectSample#2](../../mfc/codesnippet/cpp/run-time-object-model-services_3.h)]

[!code-cpp[NVC_MFCCObjectSample#3](../../mfc/codesnippet/cpp/run-time-object-model-services_4.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="implement_dyncreate"></a>  IMPLEMENT_DYNCREATE

Aktiviert die Objekte `CObject`-abgeleitete Klassen, die bei der Ausführung dynamisch erstellt werden Uhrzeit mit dem DECLARE_DYNCREATE-Makro verwendet.

```
IMPLEMENT_DYNCREATE(class_name, base_class_name)
```

### <a name="parameters"></a>Parameter

*class_name*<br/>
Der tatsächliche Name der Klasse.

*base_class_name*<br/>
Der tatsächliche Name der Basisklasse.

### <a name="remarks"></a>Hinweise

Das Framework verwendet diese Fähigkeit zum Erstellen neuer Objekte dynamisch, z. B., wenn während der Serialisierung ein Objekts vom Datenträger gelesen. Fügen Sie das IMPLEMENT_DYNCREATE-Makro in der Implementierungsdatei der Klasse hinzu. Weitere Informationen finden Sie unter [CObject-Klasse Themen](../../mfc/using-cobject.md).

Wenn Sie die DECLARE_DYNCREATE und IMPLEMENT_DYNCREATE-Makros verwenden, können Sie dann das RUNTIME_CLASS-Makro und die `CObject::IsKindOf` Memberfunktion versucht, die die Klasse der Objekte zur Laufzeit zu bestimmen.

Wenn in der Klassendeklaration DECLARE_DYNCREATE enthalten ist, muss in der klassenimplementierung IMPLEMENT_DYNCREATE enthalten sein.

Beachten Sie, dass diese Makrodefinition der Standardkonstruktor für die Klasse aufgerufen wird. Wenn ein nicht trivialen Konstruktor explizit von der Klasse implementiert wird, muss er auch den Standardkonstruktor auch explizit implementieren. Der Standardkonstruktor der Klasse hinzugefügt werden kann **private** oder **geschützt** Member Abschnitte aus, um zu verhindern, dass sie außerhalb der Implementierung der Klasse aufgerufen wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCObjectSample#22](../../mfc/codesnippet/cpp/run-time-object-model-services_5.h)]

[!code-cpp[NVC_MFCCObjectSample#23](../../mfc/codesnippet/cpp/run-time-object-model-services_6.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

## <a name="implement_olecreate_flags"></a>  IMPLEMENT_OLECREATE_FLAGS

Entweder dieses Makro oder [IMPLEMENT_OLECREATE](#implement_olecreate) muss angezeigt werden, in der Implementierungsdatei für jede Klasse, die DECLARE_OLECREATE verwendet.

### <a name="syntax"></a>Syntax

```
IMPLEMENT_OLECREATE_FLAGS( class_name, external_name, nFlags,
    l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)
```

### <a name="parameters"></a>Parameter

*class_name*<br/>
Der tatsächliche Name der Klasse.

*external_name*<br/>
Der Objektname, der für andere Anwendungen (in Anführungszeichen eingeschlossen) verfügbar gemacht wird.

*nFlags*<br/>
Enthält eine oder mehrere der folgenden Flags:

   - `afxRegInsertable` Ermöglicht das Steuerelement im Dialogfeld "Objekt einfügen" für OLE-Objekte angezeigt.
   - `afxRegApartmentThreading` Legt das threading-Modell in der Registrierung ThreadingModel = Apartment.
   - `afxRegFreeThreading` Legt das threading-Modell in der Registrierung ThreadingModel = frei.

         You can combine the two flags `afxRegApartmentThreading` and `afxRegFreeThreading` to set ThreadingModel=Both. See [InprocServer32](/windows/desktop/com/inprocserver32) in the Windows SDK for more information on threading model registration.

*l*, *w1*, *w2*, *b1*, *b2*, *b3*, *b4* , *b5*, *b6*, *b7*, *b8* Komponenten von der Klasse CLSID.

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Wenn Sie IMPLEMENT_OLECREATE_FLAGS verwenden, können Sie angeben, dass die dem Objekt unterstützt werden, mithilfe von threading-Modell die *nFlags* Parameter. Wenn Sie nur das einzelne-gehen-Modell unterstützen möchten, verwenden Sie IMPLEMENT_OLECREATE.

Der externe Name ist der Bezeichner für andere Anwendungen verfügbar gemacht. Clientanwendungen verwenden den externen Namen, um ein Objekt dieser Klasse vom Automatisierungsserver anzufordern.

Die OLE-Klassen-ID ist für das Objekt einen eindeutigen 128-Bit-Bezeichner. Es besteht aus einem **lange**zwei **WORD**s und acht **BYTE**s, dargestellt durch *l*, *w1*, *w2*, und *b1* über *b8* in der syntaxbeschreibung. Die Anwendungs-Assistenten und Code-Assistenten erstellen eindeutiger OLE-Klassen-IDs für Sie nach Bedarf.

### <a name="requirements"></a>Anforderungen

**Header:** afxdisp.h

## <a name="implementolectltype"></a>IMPLEMENT_OLECTLTYPE

Implementiert die `GetUserTypeNameID` und `GetMiscStatus` Memberfunktionen der Steuerelementklasse.

### <a name="syntax"></a>Syntax

```
DECLARE_OLECTLTYPE( class_name, idsUserTypeName, dwOleMisc )
```

### <a name="parameters"></a>Parameter

*class_name*<br/>
Der Name der Steuerelement-Klasse.

*idsUserTypeName*<br/>
Die Ressourcen-ID, der eine Zeichenfolge, die den externen Namen des Steuerelements enthält.

*dwOleMisc*<br/>
Eine Enumeration, die ein oder mehrere Flags enthält. Weitere Informationen zu dieser Enumeration finden Sie unter [OLEMISC](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc) im Windows SDK.

### <a name="remarks"></a>Hinweise

Zusätzlich zu IMPLEMENT_OLECTLTYPE müssen Sie Ihrer Klassendeklaration des Steuerelements die DECLARE_OLECTLTYPE-Makro hinzufügen.

Die `GetUserTypeNameID` Memberfunktion gibt die Ressourcenzeichenfolge, die die Steuerelementklasse identifiziert. `GetMiscStatus` Gibt die OLEMISC-Bits für das Steuerelement zurück. Diese Enumeration gibt eine Auflistung von Einstellungen, die verschiedene Merkmale des Steuerelements beschreiben. Eine vollständige Beschreibung der OLEMISC-Einstellungen finden Sie unter [OLEMISC](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc) im Windows SDK.

> [!NOTE]
>  Die Standardeinstellungen, die von der ActiveX ControlWizard verwendet werden: OLEMISC_ACTIVATEWHENVISIBLE, OLEMISC_SETCLIENTSITEFIRST, OLEMISC_INSIDEOUT, OLEMISC_CANTLINKINSIDE und OLEMISC_RECOMPOSEONRESIZE.

### <a name="requirements"></a>Anforderungen

**Header:** afxctl.h

##  <a name="implement_serial"></a>  IMPLEMENT_SERIAL

Generiert den C++-Code für eine dynamische `CObject`-Klasse mit der Run-Time-Zugriff auf den Klassennamen und die Position innerhalb der Hierarchie.

```
IMPLEMENT_SERIAL(class_name, base_class_name, wSchema)
```

### <a name="parameters"></a>Parameter

*class_name*<br/>
Der tatsächliche Name der Klasse.

*base_class_name*<br/>
Der Name der Basisklasse.

*wSchema*<br/>
Eine UINT "Versionsnummer", die im Archiv zu deserialisieren zu identifizieren und Verarbeiten von Daten, die von erstellten Programm codierenden Programm zuvor Versionen. Die Anzahl der Klasse Schema darf nicht-1 sein.

### <a name="remarks"></a>Hinweise

Verwenden Sie das IMPLEMENT_SERIAL-Makro in einem Modul .cpp; anschließend verknüpfen Sie den resultierende Objektcode nur einmal.

Können Sie das Makro AFX_API automatisch exportieren die `CArchive` Extraktionsoperator für Klassen, die DECLARE_SERIAL und IMPLEMENT_SERIAL-Makros zu verwenden. Zuordnen von Klammern Sie die Klassendeklarationen (befindet sich in der h-Datei) mit dem folgenden Code:

[!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]

Weitere Informationen finden Sie unter den [CObject-Klasse Themen](../../mfc/using-cobject.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCObjectSample#24](../../mfc/codesnippet/cpp/run-time-object-model-services_7.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="runtime_class"></a>  RUNTIME_CLASS

Ruft die Laufzeitklasse-Struktur aus den Namen einer C++-Klasse ab.

```
RUNTIME_CLASS(class_name)
```

### <a name="parameters"></a>Parameter

*class_name*<br/>
Der tatsächliche Name der Klasse (nicht in Anführungszeichen eingeschlossen).

### <a name="remarks"></a>Hinweise

RUNTIME_CLASS gibt einen Zeiger auf eine [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Struktur für die Klasse, die anhand des *Class_name*. Nur `CObject`-abgeleitete Klassen, die mit DECLARE_DYNAMIC DECLARE_DYNCREATE oder DECLARE_SERIAL deklariert gibt Zeiger auf eine `CRuntimeClass` Struktur.

Weitere Informationen finden Sie unter [CObject-Klasse Themen](../../mfc/using-cobject.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCObjectSample#25](../../mfc/codesnippet/cpp/run-time-object-model-services_8.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="declare_olecreate"></a>  DECLARE_OLECREATE

Aktiviert die Objekte `CCmdTarget`-abgeleiteten Klassen über OLE-Automatisierung erstellt werden.

```
DECLARE_OLECREATE(class_name)
```

### <a name="parameters"></a>Parameter

*class_name*<br/>
Der tatsächliche Name der Klasse.

### <a name="remarks"></a>Hinweise

Mit diesem Makro können andere OLE-fähige Anwendungen zum Erstellen von Objekten dieses Typs.

Fügen Sie der DECLARE_OLECREATE-Makro in der h-Modul für die Klasse, und klicken Sie dann schließen Sie das Modul in alle cpp-Module, die Zugriff auf Objekte dieser Klasse ein.

Wenn in der Klassendeklaration DECLARE_OLECREATE enthalten ist, muss in der klassenimplementierung IMPLEMENT_OLECREATE enthalten sein. Eine Klassendeklaration mit DECLARE_OLECREATE muss auch DECLARE_DYNCREATE oder DECLARE_SERIAL verwenden.

### <a name="requirements"></a>Anforderungen

**Header**: afxdisp.h

##  <a name="implement_olecreate"></a>  IMPLEMENT_OLECREATE

Entweder dieses Makro oder [IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags) muss angezeigt werden, in der Implementierungsdatei für jede Klasse, die verwendet `DECLARE_OLECREATE`.

```
IMPLEMENT_OLECREATE(class_name, external_name, l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)
```

### <a name="parameters"></a>Parameter

*class_name*<br/>
Der tatsächliche Name der Klasse.

*external_name*<br/>
Der Objektname, der für andere Anwendungen (in Anführungszeichen eingeschlossen) verfügbar gemacht wird.

*l*, *w1*, *w2*, *b1*, *b2*, *b3*, *b4* , *b5*, *b6*, *b7*, *b8* Komponenten von der Klasse CLSID.

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Wenn Sie IMPLEMENT_OLECREATE, in der Standardeinstellung verwenden, unterstützen Sie nur das einzelne Threadingmodell. Wenn Sie IMPLEMENT_OLECREATE_FLAGS verwenden, können Sie angeben, dass die dem Objekt unterstützt werden, mithilfe von threading-Modell die *nFlags* Parameter.

Der externe Name ist der Bezeichner für andere Anwendungen verfügbar gemacht. Clientanwendungen verwenden den externen Namen, um ein Objekt dieser Klasse vom Automatisierungsserver anzufordern.

Die OLE-Klassen-ID ist für das Objekt einen eindeutigen 128-Bit-Bezeichner. Es besteht aus einem **lange**zwei **WORD**s und acht **BYTE**s, dargestellt durch *l*, *w1*, *w2*, und *b1* über *b8* in der syntaxbeschreibung. Die Anwendungs-Assistenten und Code-Assistenten erstellen eindeutiger OLE-Klassen-IDs für Sie nach Bedarf.

### <a name="requirements"></a>Anforderungen

**Header**: afxdisp.h

## <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](mfc-macros-and-globals.md)<br/>
[Isolierung der MFC-Bibliothek für Standardsteuerelemente](../isolation-of-the-mfc-common-controls-library.md)<br/>
[CLSID-Schlüssel](/windows/desktop/com/clsid-key-hklm)
