---
title: CCommandLineInfo-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCommandLineInfo
- AFXWIN/CCommandLineInfo
- AFXWIN/CCommandLineInfo::CCommandLineInfo
- AFXWIN/CCommandLineInfo::ParseParam
- AFXWIN/CCommandLineInfo::m_bRunAutomated
- AFXWIN/CCommandLineInfo::m_bRunEmbedded
- AFXWIN/CCommandLineInfo::m_bShowSplash
- AFXWIN/CCommandLineInfo::m_nShellCommand
- AFXWIN/CCommandLineInfo::m_strDriverName
- AFXWIN/CCommandLineInfo::m_strFileName
- AFXWIN/CCommandLineInfo::m_strPortName
- AFXWIN/CCommandLineInfo::m_strPrinterName
- AFXWIN/CCommandLineInfo::m_strRestartIdentifier
dev_langs:
- C++
helpviewer_keywords:
- CCommandLineInfo [MFC], CCommandLineInfo
- CCommandLineInfo [MFC], ParseParam
- CCommandLineInfo [MFC], m_bRunAutomated
- CCommandLineInfo [MFC], m_bRunEmbedded
- CCommandLineInfo [MFC], m_bShowSplash
- CCommandLineInfo [MFC], m_nShellCommand
- CCommandLineInfo [MFC], m_strDriverName
- CCommandLineInfo [MFC], m_strFileName
- CCommandLineInfo [MFC], m_strPortName
- CCommandLineInfo [MFC], m_strPrinterName
- CCommandLineInfo [MFC], m_strRestartIdentifier
ms.assetid: 3e313ddb-0a82-4991-87ac-a27feff4668c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b7f17cf82f7dffe4ac08bd5c27a9eee6210e6010
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379020"
---
# <a name="ccommandlineinfo-class"></a>CCommandLineInfo-Klasse

Unterstützt die Analyse der Befehlszeile beim Anwendungsstart.

## <a name="syntax"></a>Syntax

```
class CCommandLineInfo : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CCommandLineInfo::CCommandLineInfo](#ccommandlineinfo)|Erstellt ein standardmäßiges `CCommandLineInfo` Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CCommandLineInfo::ParseParam](#parseparam)|Dieser Rückruf zum Analysieren der einzelnen Parameter zu überschreiben.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CCommandLineInfo::m_bRunAutomated](#m_brunautomated)|Gibt die Befehlszeile an `/Automation` Option wurde gefunden.|
|[CCommandLineInfo::m_bRunEmbedded](#m_brunembedded)|Gibt die Befehlszeile an `/Embedding` Option wurde gefunden.|
|[CCommandLineInfo::m_bShowSplash](#m_bshowsplash)|Gibt an, wenn ein Begrüßungsbildschirm angezeigt werden soll.|
|[CCommandLineInfo::m_nShellCommand](#m_nshellcommand)|Gibt an, die Shellbefehl aus, um verarbeitet werden.|
|[CCommandLineInfo::m_strDriverName](#m_strdrivername)|Gibt an, den Treiber benennen, ist der Shellbefehl Print, andernfalls leer.|
|[CCommandLineInfo::m_strFileName](#m_strfilename)|Gibt an, der Dateiname, der geöffnet oder gedruckt werden. leer, wenn es sich bei der Shellbefehl neu oder DDE-ist.|
|[CCommandLineInfo::m_strPortName](#m_strportname)|Gibt den Port benennen, ist der Shellbefehl Print, andernfalls leer.|
|[CCommandLineInfo::m_strPrinterName](#m_strprintername)|Gibt an, den Drucker benennen, ist der Shellbefehl Print, andernfalls leer.|
|[CCommandLineInfo::m_strRestartIdentifier](#m_strrestartidentifier)|Gibt den Bezeichner eindeutige Neustart für den Neustart-Manager an, wenn der Neustart-Manager die Anwendung neu gestartet.|

## <a name="remarks"></a>Hinweise

Eine MFC-Anwendung wird in der Regel erstellen Sie eine lokale Instanz dieser Klasse in der [InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) Funktion von der Application-Objekt. Dieses Objekt wird dann an übergeben [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline), die wiederholt aufruft [ParseParam](#parseparam) zum Ausfüllen der `CCommandLineInfo` Objekt. Die `CCommandLineInfo` Objekt wird dann zum übergeben [CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand) , behandeln die Befehlszeilenargumente und Flags.

Dieses Objekt können Sie um die folgenden Befehlszeilenoptionen und Parameter zu kapseln:

|Befehlszeilenargument|Ausgeführte Befehl|
|----------------------------|----------------------|
|*app*|Neue Datei.|
|*App* Dateiname|Um die Datei zu öffnen.|
|*App* `/p` Dateiname|Drucken Sie Datei auf dem Standarddrucker.|
|*App* `/pt` Filename-Druckeranschluss für Treiber|Datei mit dem angegebenen Drucker zu drucken.|
|*App* `/dde`|Starten und "await" DDE-Befehl.|
|*App* `/Automation`|Als ein OLE-Automatisierungsserver starten.|
|*App* `/Embedding`|Starten Sie ein eingebettetes OLE-Element zu bearbeiten.|
|*App* `/Register`<br /><br /> *App* `/Regserver`|Informiert die Anwendung aus, um alle Registrierungsaufgaben durchzuführen.|
|*App* `/Unregister`<br /><br /> *App* `/Unregserver`|Informiert die Anwendung aus, um alle Aufgaben für die Aufhebung der Registrierung durchzuführen.|

Leiten Sie eine neue Klasse von `CCommandLineInfo` anderen Flags und Parameterwerte zu behandeln. Außer Kraft setzen [ParseParam](#parseparam) , behandeln die neuen Flags.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CCommandLineInfo`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="ccommandlineinfo"></a>  CCommandLineInfo::CCommandLineInfo

Dieser Konstruktor erstellt ein `CCommandLineInfo` -Objekt mit Standardwerten.

```
CCommandLineInfo();
```

### <a name="remarks"></a>Hinweise

Standardmäßig wird der Begrüßungsbildschirm angezeigt werden ( `m_bShowSplash=TRUE`) und den neuen Befehl im Menü Datei auszuführen ( `m_nShellCommand` **= NewFile**).

Ruft die Anwendung-Framework [ParseParam](#parseparam) Data Member dieses Objekts zu füllen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#54](../../mfc/codesnippet/cpp/ccommandlineinfo-class_1.cpp)]

##  <a name="m_brunautomated"></a>  CCommandLineInfo::m_bRunAutomated

Gibt an, dass die `/Automation` Flag wurde in der Befehlszeile gefunden.

```
BOOL m_bRunAutomated;
```

### <a name="remarks"></a>Hinweise

Bei "true", bedeutet dies als OLE-Automatisierungsserver starten.

##  <a name="m_brunembedded"></a>  CCommandLineInfo::m_bRunEmbedded

Gibt an, dass die `/Embedding` Flag wurde in der Befehlszeile gefunden.

```
BOOL m_bRunEmbedded;
```

### <a name="remarks"></a>Hinweise

Bei "true", bedeutet dies für die Bearbeitung von eines eingebetteten OLE-Elements gestartet.

##  <a name="m_bshowsplash"></a>  CCommandLineInfo::m_bShowSplash

Gibt an, dass der Begrüßungsbildschirm angezeigt werden soll.

```
BOOL m_bShowSplash;
```

### <a name="remarks"></a>Hinweise

Bei "true", bedeutet dies, dass während des Starts der Begrüßungsbildschirm für diese Anwendung angezeigt werden sollen. Die standardmäßige Implementierung des [ParseParam](#parseparam) dieses Datenelement auf "true" legt [M_nShellCommand](#m_nshellcommand) gleich `CCommandLineInfo::FileNew`.

##  <a name="m_nshellcommand"></a>  CCommandLineInfo::m_nShellCommand

Gibt den Befehl "Shell" für diese Instanz der Anwendung an.

```
m_nShellCommand;
```

### <a name="remarks"></a>Hinweise

Der Typ für dieses Datenelement ist den folgenden Aufzählungstyp, definiert in den die `CCommandLineInfo` Klasse.

```
enum {
    FileNew,
    FileOpen,
    FilePrint,
    FilePrintTo,
    FileDDE,
    AppRegister,
    AppUnregister,
    RestartByRestartManager,
    FileNothing = -1
    };
```

Eine kurze Beschreibung dieser Werte finden Sie in der folgende Liste.

- `CCommandLineInfo::FileNew` Gibt an, dass kein Dateiname in der Befehlszeile angegeben wurde.

- `CCommandLineInfo::FileOpen` Gibt an, dass in der Befehlszeile ein Dateiname gefunden wurde und keine der folgenden Flags in der Befehlszeile gefunden wurden: `/p`, `/pt`, `/dde`.

- `CCommandLineInfo::FilePrint` Gibt an, dass die `/p` Flag wurde in der Befehlszeile gefunden.

- `CCommandLineInfo::FilePrintTo` Gibt an, dass die `/pt` Flag wurde in der Befehlszeile gefunden.

- `CCommandLineInfo::FileDDE` Gibt an, dass die `/dde` Flag wurde in der Befehlszeile gefunden.

- `CCommandLineInfo::AppRegister` Gibt an, dass die `/Register` oder `/Regserver` Flag wurde gefunden, in der Befehlszeile und die Anwendung wurde aufgefordert, zu registrieren.

- `CCommandLineInfo::AppUnregister` Gibt an, dass die `/Unregister` oder `/Unregserver` Anwendung wurde beim Aufheben der Registrierung aufgefordert.

- `CCommandLineInfo::RestartByRestartManager` Gibt an, dass die Anwendung vom Neustart-Manager neu gestartet wurde.

- `CCommandLineInfo::FileNothing` Deaktiviert die Anzeige von einer neuen untergeordneten MDI-Fensters auf Start. Programmbedingt anzeigen Anwendungs-Assistenten generierte MDI-Anwendungen ein neues untergeordnetes Fenster beim Start an. Um dieses Feature deaktivieren, können Sie eine Anwendung `CCommandLineInfo::FileNothing` wie beim Aufruf der Shellbefehl [ProcessShellCommand erforderlich](../../mfc/reference/cwinapp-class.md#processshellcommand). `ProcessShellCommand` wird aufgerufen, indem die `InitInstance( )` aller `CWinApp` abgeleiteten Klassen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#55](../../mfc/codesnippet/cpp/ccommandlineinfo-class_2.cpp)]

##  <a name="m_strdrivername"></a>  CCommandLineInfo::m_strDriverName

Speichert den Wert des dritten Parameters nicht-Flag in der Befehlszeile an.

```
CString m_strDriverName;
```

### <a name="remarks"></a>Hinweise

Dieser Parameter ist in der Regel der Name des Druckertreibers für einen Druckserver auf Shell-Befehl. Die standardmäßige Implementierung des [ParseParam](#parseparam) legt dieser Datenmember nur, wenn die `/pt` Flag wurde in der Befehlszeile gefunden.

##  <a name="m_strfilename"></a>  CCommandLineInfo::m_strFileName

Speichert den Wert des ersten Parameters nicht-Flag in der Befehlszeile an.

```
CString m_strFileName;
```

### <a name="remarks"></a>Hinweise

Dieser Parameter ist in der Regel der Name des zu öffnenden Datei.

##  <a name="m_strportname"></a>  CCommandLineInfo::m_strPortName

Speichert den Wert des vierten Parameters nicht-Flag in der Befehlszeile an.

```
CString m_strPortName;
```

### <a name="remarks"></a>Hinweise

Dieser Parameter ist in der Regel den Namen des Ports für einen Druckserver auf Shell-Befehl. Die standardmäßige Implementierung des [ParseParam](#parseparam) legt dieser Datenmember nur, wenn die `/pt` Flag wurde in der Befehlszeile gefunden.

##  <a name="m_strprintername"></a>  CCommandLineInfo::m_strPrinterName

Speichert den Wert des zweiten Parameters nicht-Flag in der Befehlszeile an.

```
CString m_strPrinterName;
```

### <a name="remarks"></a>Hinweise

Dieser Parameter ist in der Regel der Name des Druckers für einen Druckserver auf Shell-Befehl. Die standardmäßige Implementierung des [ParseParam](#parseparam) legt dieser Datenmember nur, wenn die `/pt` Flag wurde in der Befehlszeile gefunden.

##  <a name="m_strrestartidentifier"></a>  CCommandLineInfo::m_strRestartIdentifier

Die eindeutige neu Bezeichner in der Befehlszeile starten.

```
CString m_strRestartIdentifier;
```

### <a name="remarks"></a>Hinweise

Die Neustart-ID ist für jede Instanz der Anwendung eindeutig.

Wenn der Neustart-Manager die Anwendung beendet und einen Neustart konfiguriert wird, führt der Neustart-Manager die Anwendung über die Befehlszeile mit der Restart-ID als optionalen Parameter an. Wenn der Neustart-Manager den Neustart-Bezeichner verwendet wird, kann die Anwendung die vorher geöffnete Dokumente öffnen und automatisch gespeicherte Dateien wiederherstellen.

##  <a name="parseparam"></a>  CCommandLineInfo::ParseParam

Das Framework ruft diese Funktion, um die Analyse/einzelne Parameter über die Befehlszeile zu interpretieren. Die zweite Version, die von der ersten unterscheidet sich nur in Unicode-Projekten.

```
virtual void ParseParam(
    const char* pszParam,
    BOOL bFlag,
    BOOL bLast);


virtual void ParseParam(
    const TCHAR* pszParam,
    BOOL bFlag,
    BOOL bLast);
```

### <a name="parameters"></a>Parameter

*pszParam*<br/>
Der Parameter oder -Flag.

*bFlag*<br/>
Gibt an, ob *PszParam* ist ein Parameter oder ein Flag.

*bLast*<br/>
Gibt an, ob dies der letzte Parameter oder -Flag in der Befehlszeile.

### <a name="remarks"></a>Hinweise

[CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline) Aufrufe `ParseParam` einmal für jeden Parameter oder ein Flag in der Befehlszeile, um als Argument übergeben *PszParam*. Wenn das erste Zeichen des Parameters ist ein " **-**"oder ein" **/**", er entfernt wird und *bFlag* auf "true" festgelegt ist. Beim Analysieren des letzten Parameters, *bLast* auf "true" festgelegt ist.

Die Standardimplementierung dieser Funktion erkennt die folgenden Flags: `/p`, `/pt`, `/dde`, `/Automation`, und `/Embedding`, wie in der folgenden Tabelle dargestellt:

|Befehlszeilenargument|Ausgeführte Befehl|
|----------------------------|----------------------|
|*app*|Neue Datei.|
|*App* Dateiname|Um die Datei zu öffnen.|
|*App* `/p` Dateiname|Drucken Sie Datei auf dem Standarddrucker.|
|*App* `/pt` Filename-Druckeranschluss für Treiber|Datei mit dem angegebenen Drucker zu drucken.|
|*App* `/dde`|Starten und "await" DDE-Befehl.|
|*App* `/Automation`|Als ein OLE-Automatisierungsserver starten.|
|*App* `/Embedding`|Starten Sie ein eingebettetes OLE-Element zu bearbeiten.|
|*App* `/Register`<br /><br /> *App* `/Regserver`|Informiert die Anwendung aus, um alle Registrierungsaufgaben durchzuführen.|
|*App* `/Unregister`<br /><br /> *App* `/Unregserver`|Informiert die Anwendung aus, um alle Aufgaben für die Aufhebung der Registrierung durchzuführen.|

Diese Informationen werden gespeichert, [M_bRunAutomated](#m_brunautomated), [M_bRunEmbedded](#m_brunembedded), und [M_nShellCommand](#m_nshellcommand). Flags werden markiert, entweder einen Schrägstrich ' **/**'oder Bindestrich' **-**".

Die standardmäßige Implementierung setzt den ersten nicht-Flag-Parameter in [M_strFileName](#m_strfilename). Im Fall von der `/pt` Flags, die standardmäßige Implementierung setzt das zweite, dritte und vierte nicht-Flag-Parameter in [M_strPrinterName](#m_strprintername), [M_strDriverName](#m_strdrivername), und [M_ StrPortName](#m_strportname)bzw.

Die standardmäßige Implementierung setzt auch [M_bShowSplash](#m_bshowsplash) auf "true" nur bei einer neuen Datei. Bei einer neuen Datei hat der Benutzer im Zusammenhang mit der Anwendung selbst Aktion. In allen anderen Fällen, einschließlich Öffnen von vorhandenen Dateien, die mithilfe der Shell umfasst die Benutzeraktion direkt die Datei. In eine dokumentorientierte Standpunkt aus betrachtet muss der Begrüßungsbildschirm nicht, die Anwendung gestartet, ankündigen zu können.

Überschreiben Sie diese Funktion in der abgeleiteten Klasse andere Kennzeichen und Parameter-Werte behandelt werden.

## <a name="see-also"></a>Siehe auch

[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline)<br/>
[CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)

