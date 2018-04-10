---
title: CAtlExeModuleT-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
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
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c45b1f95aba4f11e6995bf5c4c1cfff00627e4b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="catlexemodulet-class"></a>CAtlExeModuleT-Klasse
Diese Klasse stellt das Modul für eine Anwendung.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
class ATL_NO_VTABLE CAtlExeModuleT : public CAtlModuleT<T>
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
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
|[CAtlExeModuleT](#initializecom)|Initialisiert COM.|  
|[CAtlExeModuleT::ParseCommandLine](#parsecommandline)|Analysiert die Befehlszeile und führt die Registrierung bei Bedarf.|  
|[CAtlExeModuleT::PostMessageLoop](#postmessageloop)|Diese Methode wird aufgerufen, unmittelbar nach dem Beenden der Nachrichtenschleife.|  
|[CAtlExeModuleT::PreMessageLoop](#premessageloop)|Diese Methode wird aufgerufen, unmittelbar vor die Nachrichtenschleife eingeben.|  
|[CAtlExeModuleT::RegisterClassObjects](#registerclassobjects)|Registriert das Klassenobjekt.|  
|[CAtlExeModuleT::RevokeClassObjects](#revokeclassobjects)|Hebt das Klassenobjekt.|  
|[CAtlExeModuleT::Run](#run)|Diese Methode führt der Code im Modul "EXE" führen Sie die Nachrichtenschleife zu initialisieren und bereinigen.|  
|[CAtlExeModuleT::RunMessageLoop](#runmessageloop)|Diese Methode führt die Nachrichtenschleife.|  
|[CAtlExeModuleT::UninitializeCom](#uninitializecom)|Hebt die Initialisierung COM.|  
|[CAtlExeModuleT::Unlock](#unlock)|Verringert die Sperrenanzahl des Moduls.|  
|[CAtlExeModuleT::WinMain](#winmain)|Diese Methode implementiert den Code zum Ausführen einer EXE-Datei erforderlich.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown)|Ein Flag gibt an, dass es darf eine Verzögerung, die das Modul heruntergefahren wird.|  
|[CAtlExeModuleT::m_dwPause](#m_dwpause)|Eine Pause-Wert verwendet, um sicherzustellen, dass alle Objekte vor dem Herunterfahren freigegeben werden.|  
|[CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout)|Ein Timeoutwert verwendet, um das Entladen des Moduls zu verzögern.|  
  
## <a name="remarks"></a>Hinweise  
 `CAtlExeModuleT`Stellt das Modul für eine Anwendung (EXE) und enthält Code, der unterstützt beim Beenden eine EXE-Datei erstellen, Verarbeiten der Befehlszeile Klassenobjekte zu registrieren, die Nachrichtenschleife ausgeführt und bereinigen.  
  
 Diese Klasse dient zur Verbesserung der Leistung bei der COM-Objekten in der EXE-Server kontinuierlich erstellt und zerstört werden. Nachdem das letzte COM-Objekt veröffentlicht wird, wartet die EXE-Datei für eine Dauer von angegebenen der [CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout) -Datenmember. Wenn während dieses Zeitraums keine Aktivität vorhanden ist (d. h. keine COM-Objekte erstellt werden), wird der Prozess des Herunterfahrens initiiert.  
  
 Die [CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown) -Datenmember ist ein Flag, das verwendet wird, um festzustellen, ob die EXE-Datei den oben definierten Mechanismus verwenden soll. Wenn sie auf "false" festgelegt ist, wird das Modul sofort beendet.  
  
 Weitere Informationen zu Modulen in ATL finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  

  
 [Von CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CAtlExeModuleT`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="catlexemodulet"></a>CAtlExeModuleT::CAtlExeModuleT  
 Der Konstruktor.  
  
```
CAtlExeModuleT() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Modul für die EXE-Datei nicht initialisiert werden konnte, wird sofort WinMain zurückgegeben, ohne weitere Verarbeitung.  
  
##  <a name="dtor"></a>CAtlExeModuleT:: ~ CAtlExeModuleT  
 Der Destruktor.  
  
```
~CAtlExeModuleT() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordnete Ressourcen frei.  
  
##  <a name="initializecom"></a>CAtlExeModuleT  
 Initialisiert COM.  
  
```
static HRESULT InitializeCom() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Konstruktor aufgerufen und kann überschrieben werden, um das Initialisieren von COM in einer Weise, die die standardmäßige Implementierung unterscheidet. Die standardmäßige Implementierung entweder ruft **CoInitializeEx (NULL, COINIT_MULTITHREADED)** oder **CoInitialize(NULL)** abhängig von der Projektkonfiguration.  
  
 Überschreiben diese Methode normalerweise erfordert überschreiben [CAtlExeModuleT::UninitializeCom](#uninitializecom).  
  
##  <a name="m_bdelayshutdown"></a>CAtlExeModuleT::m_bDelayShutdown  
 Ein Flag gibt an, dass es darf eine Verzögerung, die das Modul heruntergefahren wird.  
  
```
bool m_bDelayShutdown;
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter der [CAtlExeModuleT-Übersicht über](../../atl/reference/catlexemodulet-class.md) für Details.  
  
##  <a name="m_dwpause"></a>CAtlExeModuleT::m_dwPause  
 Eine Pause-Wert verwendet, um sicherzustellen, dass alle Objekte vor dem Herunterfahren überschritten werden.  
  
```
DWORD m_dwPause;
```  
  
### <a name="remarks"></a>Hinweise  
 Ändern Sie diesen Wert nach dem Aufruf [CAtlExeModuleT](#initializecom) , legen Sie die Anzahl der Millisekunden, die als die Pause-Wert für das Herunterfahren des Servers verwendet. Der Standardwert beträgt 1.000 Millisekunden.  
  
##  <a name="m_dwtimeout"></a>CAtlExeModuleT::m_dwTimeOut  
 Ein Timeoutwert verwendet, um das Entladen des Moduls zu verzögern.  
  
```
DWORD m_dwTimeOut;
```  
  
### <a name="remarks"></a>Hinweise  
 Ändern Sie diesen Wert nach dem Aufruf [CAtlExeModuleT](#initializecom) definieren die Anzahl der Millisekunden, die als der Timeoutwert für das Herunterfahren des Servers verwendet. Der Standardwert ist 5000 Millisekunden. Finden Sie unter der [CAtlExeModuleT-Übersicht](../../atl/reference/catlexemodulet-class.md) Weitere Details.  
  
##  <a name="parsecommandline"></a>CAtlExeModuleT::ParseCommandLine  
 Analysiert die Befehlszeile und führt die Registrierung bei Bedarf.  
  
```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpCmdLine`  
 Die Befehlszeile, die an die Anwendung übergeben werden.  
  
 `pnRetCode`  
 Die Registrierung (falls es stattgefunden hat) entsprechende HRESULT.  
  
### <a name="return-value"></a>Rückgabewert  
 "True" zurück, wenn die Anwendung fortgesetzt werden soll, andernfalls "false" ausgeführt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, von [CAtlExeModuleT::WinMain](#winmain) und kann überschrieben werden, um die Befehlszeilenoptionen zu behandeln. Die standardmäßige Implementierung überprüft, ob **/RegServer** und **/Unregserver** Befehlszeilenargumente und führt eine Registrierung oder Aufheben der Registrierung.  
  
##  <a name="postmessageloop"></a>CAtlExeModuleT::PostMessageLoop  
 Diese Methode wird aufgerufen, unmittelbar nach dem Beenden der Nachrichtenschleife.  
  
```
HRESULT PostMessageLoop() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um die benutzerdefinierte Anwendung Cleanup auszuführen. Die Standardimplementierung ruft [CAtlExeModuleT::RevokeClassObjects](#revokeclassobjects).  
  
##  <a name="premessageloop"></a>CAtlExeModuleT::PreMessageLoop  
 Diese Methode wird aufgerufen, unmittelbar vor die Nachrichtenschleife eingeben.  
  
```
HRESULT PreMessageLoop(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nShowCmd`  
 Der angegebene Wert als die `nShowCmd` Parameter im WinMain.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um die angepasste Initialisierung von Code für die Anwendung hinzuzufügen. Die standardmäßige Implementierung registriert die Objekte der Klasse.  
  
##  <a name="registerclassobjects"></a>CAtlExeModuleT::RegisterClassObjects  
 Das Klassenobjekt registriert mit OLE, damit andere Anwendungen hergestellt werden können.  
  
```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *dwClsContext*  
 Gibt den Kontext, in dem das Klassenobjekt ist, ausgeführt werden. Mögliche Werte sind CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER oder CLSCTX_LOCAL_SERVER.  
  
 `dwFlags`  
 Bestimmt die Verbindungstypen auf das Klassenobjekt. Mögliche Werte sind REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE oder REGCLS_MULTI_SEPARATE.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK zurückgegeben, auf Erfolg "S_FALSE" gäbe es keine Klassen zum Registrieren oder einen HRESULT-Fehler bei einem Fehler.  
  
##  <a name="revokeclassobjects"></a>CAtlExeModuleT::RevokeClassObjects  
 Entfernt das Klassenobjekt.  
  
```
HRESULT RevokeClassObjects() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK zurückgegeben, auf Erfolg "S_FALSE" gäbe es keine Klassen zum Registrieren oder einen HRESULT-Fehler bei einem Fehler.  
  
##  <a name="run"></a>CAtlExeModuleT::Run  
 Diese Methode führt der Code im Modul "EXE" führen Sie die Nachrichtenschleife zu initialisieren und bereinigen.  
  
```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nShowCmd`  
 Gibt an, wie das Fenster angezeigt werden. Dieser Parameter kann einen der Werte im erläutert die [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) Abschnitt. Der Standardwert ist SW_HIDE.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann überschrieben werden. Allerdings in der Praxis ist es besser, außer Kraft setzen [CAtlExeModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::RunMessageLoop](#runmessageloop), oder [CAtlExeModuleT::PostMessageLoop](#postmessageloop) Stattdessen.  
  
##  <a name="runmessageloop"></a>CAtlExeModuleT::RunMessageLoop  
 Diese Methode führt die Nachrichtenschleife.  
  
```
void RunMessageLoop() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann überschrieben werden, um das Verhalten der Meldungsschleife ändern.  
  
##  <a name="uninitializecom"></a>CAtlExeModuleT::UninitializeCom  
 Hebt die Initialisierung COM.  
  
```
static void UninitializeCom() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig ruft diese Methode einfach [CoUninitialize](http://msdn.microsoft.com/library/windows/desktop/ms688715) und der Destruktor aufgerufen wird. Überschreiben Sie diese Methode, wenn Sie außer Kraft setzen [CAtlExeModuleT](#initializecom).  
  
##  <a name="unlock"></a>CAtlExeModuleT::Unlock  
 Verringert die Sperrenanzahl des Moduls.  
  
```
LONG Unlock() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert, der möglicherweise bei der Diagnose hilfreich oder testen.  
  
##  <a name="winmain"></a>CAtlExeModuleT::WinMain  
 Diese Methode implementiert den Code zum Ausführen einer EXE-Datei erforderlich.  
  
```
int WinMain(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nShowCmd`  
 Gibt an, wie das Fenster angezeigt werden. Dieser Parameter kann einen der Werte im erläutert die [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) Abschnitt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die ausführbare-Rückgabewert zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann überschrieben werden. Wenn außer Kraft gesetzt [CAtlExeModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::PostMessageLoop](#postmessageloop), oder [CAtlExeModuleT::RunMessageLoop](#runmessageloop) stellt keine ausreichende Flexibilität bereit , es ist möglich, überschreiben die `WinMain` funktionieren mit dieser Methode.  
  
## <a name="see-also"></a>Siehe auch  
 [ATLDuck-Beispiel](../../visual-cpp-samples.md)   
 [CAtlModuleT-Klasse](../../atl/reference/catlmodulet-class.md)   
 [CAtlDllModuleT-Klasse](../../atl/reference/catldllmodulet-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
