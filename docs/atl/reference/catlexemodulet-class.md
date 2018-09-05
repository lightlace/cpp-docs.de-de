---
title: CAtlExeModuleT-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT::CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT::InitializeCom
- ATLBASE/ATL::CAtlExeModuleT::ParseCommandLine
- ATLBASE/ATL::CAtlExeModuleT::PostMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::PreMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::RegisterClassObjects
- ATLBASE/ATL::CAtlExeModuleT::RevokeClassObjects
- ATLBASE/ATL::CAtlExeModuleT::Run
- ATLBASE/ATL::CAtlExeModuleT::RunMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::UninitializeCom
- ATLBASE/ATL::CAtlExeModuleT::Unlock
- ATLBASE/ATL::CAtlExeModuleT::WinMain
- ATLBASE/ATL::CAtlExeModuleT::m_bDelayShutdown
- ATLBASE/ATL::CAtlExeModuleT::m_dwPause
- ATLBASE/ATL::CAtlExeModuleT::m_dwTimeOut
dev_langs:
- C++
helpviewer_keywords:
- CAtlExeModuleT class
ms.assetid: 82245f3d-91d4-44fa-aa86-7cc7fbd758d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aa212a6a58d1de417035f002b2caf3e206dabf1c
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757584"
---
# <a name="catlexemodulet-class"></a>CAtlExeModuleT-Klasse

Diese Klasse stellt das Modul für eine Anwendung.

## <a name="syntax"></a>Syntax

```
template <class T>  
class ATL_NO_VTABLE CAtlExeModuleT : public CAtlModuleT<T>
```

#### <a name="parameters"></a>Parameter

*T*  
Die Klasse abgeleitet `CAtlExeModuleT`.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAtlExeModuleT::CAtlExeModuleT](#catlexemodulet)|Der Konstruktor.|
|[CAtlExeModuleT:: ~ CAtlExeModuleT](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAtlExeModuleT](#initializecom)|Initialisiert die COM.|
|[CAtlExeModuleT::ParseCommandLine](#parsecommandline)|Analysiert die Befehlszeile und führt die Registrierung bei Bedarf.|
|[CAtlExeModuleT::PostMessageLoop](#postmessageloop)|Diese Methode wird aufgerufen, unmittelbar nach die Nachrichtenschleife beendet wird.|
|[CAtlExeModuleT::PreMessageLoop](#premessageloop)|Diese Methode wird aufgerufen, unmittelbar vor die Nachrichtenschleife eingeben.|
|[CAtlExeModuleT::RegisterClassObjects](#registerclassobjects)|Registriert das Klassenobjekt.|
|[CAtlExeModuleT::RevokeClassObjects](#revokeclassobjects)|Widerruft das Klassenobjekt.|
|[CAtlExeModuleT::Run](#run)|Diese Methode Code im Modul exe-Datei initialisiert werden, führen Sie die Meldungsschleife ausführt, und bereinigen Sie.|
|[CAtlExeModuleT::RunMessageLoop](#runmessageloop)|Diese Methode führt die Nachrichtenschleife.|
|[CAtlExeModuleT::UninitializeCom](#uninitializecom)|Hebt die Initialisierung COM.|
|[CAtlExeModuleT::Unlock](#unlock)|Verringert die Sperrenanzahl des Moduls.|
|[CAtlExeModuleT::WinMain](#winmain)|Diese Methode implementiert den erforderlichen Code für eine EXE-Datei ausführen.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown)|Ein Flag, das angibt, dass es sollte eine Verzögerung, die das Modul wird heruntergefahren.|
|[CAtlExeModuleT::m_dwPause](#m_dwpause)|Ein Anhalten-Wert verwendet, um sicherzustellen, dass alle Objekte vor dem Herunterfahren freigegeben werden.|
|[CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout)|Ein Timeoutwert verwendet, um das Entladen des Moduls zu verzögern.|

## <a name="remarks"></a>Hinweise

`CAtlExeModuleT` Stellt das Modul für eine Anwendung (EXE), und enthält Code, der eine EXE-Datei erstellen, Verarbeiten der Befehlszeile, Registrieren von Klassenobjekten, die Meldungsschleife ausführt und Bereinigen von Exit unterstützt.

Diese Klasse dient zur Verbesserung der Leistung bei der COM-Objekte in der EXE-Server ständig erstellt und zerstört werden. Nach das letzte COM-Objekt veröffentlicht wird, wartet die EXE-Datei für eine Dauer, die gemäß der [CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout) -Datenmember. Wenn in diesem Zeitraum keine Aktivität vorhanden ist (d. h. keine COM-Objekte werden erstellt), wird der Prozess des Herunterfahrens initiiert.

Die [CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown) -Datenmember ist ein Flag, das verwendet, um zu bestimmen, ob die EXE-Datei mit den oben definierten Mechanismus verwenden soll. Wenn sie auf "false" festgelegt ist, wird das Modul sofort beendet.

Weitere Informationen zu Modulen in ATL, finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[_ATL_MODULE](atl-typedefs.md#_atl_module)  

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

`CAtlExeModuleT`

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="catlexemodulet"></a>  CAtlExeModuleT::CAtlExeModuleT

Der Konstruktor.

```
CAtlExeModuleT() throw();
```

### <a name="remarks"></a>Hinweise

Wenn die EXE-Modul nicht initialisiert werden konnte, wird sofort WinMain zurückgegeben, ohne weitere Verarbeitung.

##  <a name="dtor"></a>  CAtlExeModuleT:: ~ CAtlExeModuleT

Der Destruktor.

```
~CAtlExeModuleT() throw();
```

### <a name="remarks"></a>Hinweise

Gibt alle zugeordnete Ressourcen frei.

##  <a name="initializecom"></a>  CAtlExeModuleT

Initialisiert die COM.

```
static HRESULT InitializeCom() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Diese Methode wird vom Konstruktor aufgerufen und kann überschrieben werden, um das Initialisieren von COM in einer Weise, die die standardmäßige Implementierung unterscheidet. Die standardmäßige Implementierung entweder ruft `CoInitializeEx(NULL, COINIT_MULTITHREADED)` oder `CoInitialize(NULL)` je nach der Konfiguration des Projekts.

Überschreiben diese Methode normalerweise erfordert überschreiben [CAtlExeModuleT::UninitializeCom](#uninitializecom).

##  <a name="m_bdelayshutdown"></a>  CAtlExeModuleT::m_bDelayShutdown

Ein Flag, das angibt, dass es sollte eine Verzögerung, die das Modul wird heruntergefahren.

```
bool m_bDelayShutdown;
```

### <a name="remarks"></a>Hinweise

Finden Sie unter den [CAtlExeModuleT Übersicht](../../atl/reference/catlexemodulet-class.md) Details.

##  <a name="m_dwpause"></a>  CAtlExeModuleT::m_dwPause

Ein Anhalten-Wert verwendet, um sicherzustellen, dass alle Objekte vor dem Herunterfahren durchgeführt werden.

```
DWORD m_dwPause;
```

### <a name="remarks"></a>Hinweise

Ändern Sie diesen Wert nach dem Aufruf [CAtlExeModuleT](#initializecom) festlegen die Anzahl der Millisekunden, die als der Pause-Wert für das Herunterfahren des Servers verwendet. Der Standardwert ist 1000 Millisekunden.

##  <a name="m_dwtimeout"></a>  CAtlExeModuleT::m_dwTimeOut

Ein Timeoutwert verwendet, um das Entladen des Moduls zu verzögern.

```
DWORD m_dwTimeOut;
```

### <a name="remarks"></a>Hinweise

Ändern Sie diesen Wert nach dem Aufruf [CAtlExeModuleT](#initializecom) definieren die Anzahl der Millisekunden, die als der Timeoutwert für das Herunterfahren des Servers verwendet. Der Standardwert ist 5000 Millisekunden. Finden Sie unter den [CAtlExeModuleT Übersicht](../../atl/reference/catlexemodulet-class.md) Weitere Details.

##  <a name="parsecommandline"></a>  CAtlExeModuleT::ParseCommandLine

Analysiert die Befehlszeile und führt die Registrierung bei Bedarf.

```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```

### <a name="parameters"></a>Parameter

*lpCmdLine*  
Die Befehlszeile, die an die Anwendung übergeben werden.

*pnRetCode*  
Das HRESULT der Registrierung (wenn es stattgefunden hat).

### <a name="return-value"></a>Rückgabewert

True zurück, wenn die Anwendung fortgesetzt werden soll, andernfalls "false" ausgeführt.

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, von [CAtlExeModuleT::WinMain](#winmain) und zum Behandeln von Befehlszeilenschaltern überschrieben werden können. Die standardmäßige Implementierung überprüft **/RegServer** und **/Unregserver** Befehlszeilenargumente und führt Eintragung oder Aufheben der Registrierung.

##  <a name="postmessageloop"></a>  CAtlExeModuleT::PostMessageLoop

Diese Methode wird aufgerufen, unmittelbar nach die Nachrichtenschleife beendet wird.

```
HRESULT PostMessageLoop() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, um die benutzerdefinierte Anwendung Bereinigung durchführen. Die Standardimplementierung ruft [CAtlExeModuleT::RevokeClassObjects](#revokeclassobjects).

##  <a name="premessageloop"></a>  CAtlExeModuleT::PreMessageLoop

Diese Methode wird aufgerufen, unmittelbar vor die Nachrichtenschleife eingeben.

```
HRESULT PreMessageLoop(int nShowCmd) throw();
```

### <a name="parameters"></a>Parameter

*nShowCmd*  
Der Wert, der als übergeben die *nShowCmd* WinMain Parameter.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, um die angepasste Initialisierung von Code für die Anwendung hinzuzufügen. Die Standardimplementierung registriert die Objekte der Klasse.

##  <a name="registerclassobjects"></a>  CAtlExeModuleT::RegisterClassObjects

Das Klassenobjekt registriert mit OLE, damit andere Anwendungen hergestellt werden können.

```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```

### <a name="parameters"></a>Parameter

*dwClsContext*  
Gibt den Kontext, in dem das Klassenobjekt ist, ausgeführt werden. Mögliche Werte sind CLSCTX_INPROC_SERVER CLSCTX_INPROC_HANDLER oder CLSCTX_LOCAL_SERVER.

*dwFlags*  
Bestimmt die Art der Verbindung mit dem Klassenobjekt. Mögliche Werte sind REGCLS_SINGLEUSE REGCLS_MULTIPLEUSE oder REGCLS_MULTI_SEPARATE.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg, S_FALSE, wenn gab es keine Klassen zum Registrieren oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="revokeclassobjects"></a>  CAtlExeModuleT::RevokeClassObjects

Entfernt das Klassenobjekt.

```
HRESULT RevokeClassObjects() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg, S_FALSE, wenn gab es keine Klassen zum Registrieren oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="run"></a>  CAtlExeModuleT::Run

Diese Methode Code im Modul exe-Datei initialisiert werden, führen Sie die Meldungsschleife ausführt, und bereinigen Sie.

```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```

### <a name="parameters"></a>Parameter

*nShowCmd*  
Gibt an, wie das Fenster angezeigt werden. Dieser Parameter kann sein, einen der Werte in erläutert die [WinMain](https://msdn.microsoft.com/library/windows/desktop/ms633559) Abschnitt. Der Standardwert ist SW_HIDE.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Diese Methode kann überschrieben werden. Allerdings in der Praxis ist es besser, außer Kraft setzen [CAtlExeModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::RunMessageLoop](#runmessageloop), oder [CAtlExeModuleT::PostMessageLoop](#postmessageloop) Stattdessen verwenden.

##  <a name="runmessageloop"></a>  CAtlExeModuleT::RunMessageLoop

Diese Methode führt die Nachrichtenschleife.

```
void RunMessageLoop() throw();
```

### <a name="remarks"></a>Hinweise

Diese Methode kann überschrieben werden, um das Verhalten der Meldungsschleife ändern.

##  <a name="uninitializecom"></a>  CAtlExeModuleT::UninitializeCom

Hebt die Initialisierung COM.

```
static void UninitializeCom() throw();
```

### <a name="remarks"></a>Hinweise

Standardmäßig ruft diese Methode einfach [CoUninitialize](/windows/desktop/api/combaseapi/nf-combaseapi-couninitialize) und der Destruktor aufgerufen wird. Diese Methode überschreiben, wenn Sie außer Kraft setzen [CAtlExeModuleT](#initializecom).

##  <a name="unlock"></a>  CAtlExeModuleT::Unlock

Verringert die Sperrenanzahl des Moduls.

```
LONG Unlock() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Wert, der möglicherweise bei der Diagnose hilfreich oder Tests zurück.

##  <a name="winmain"></a>  CAtlExeModuleT::WinMain

Diese Methode implementiert den erforderlichen Code für eine EXE-Datei ausführen.

```
int WinMain(int nShowCmd) throw();
```

### <a name="parameters"></a>Parameter

*nShowCmd*  
Gibt an, wie das Fenster angezeigt werden. Dieser Parameter kann sein, einen der Werte in erläutert die [WinMain](https://msdn.microsoft.com/library/windows/desktop/ms633559) Abschnitt.

### <a name="return-value"></a>Rückgabewert

Gibt die ausführbare Datei der Rückgabewert zurück.

### <a name="remarks"></a>Hinweise

Diese Methode kann überschrieben werden. Wenn außer Kraft gesetzt [CAtlExeModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::PostMessageLoop](#postmessageloop), oder [CAtlExeModuleT::RunMessageLoop](#runmessageloop) stellt keine ausreichende Flexibilität bereit , es ist möglich, überschreiben die `WinMain` funktionieren mit dieser Methode.

## <a name="see-also"></a>Siehe auch

[Beispiel für ATLDuck](../../visual-cpp-samples.md)   
[CAtlModuleT-Klasse](../../atl/reference/catlmodulet-class.md)   
[CAtlDllModuleT-Klasse](../../atl/reference/catldllmodulet-class.md)   
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
