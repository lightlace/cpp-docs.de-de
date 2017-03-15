---
title: CAtlExeModuleT-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAtlExeModuleT<T>
- CAtlExeModuleT
- ATL.CAtlExeModuleT<T>
- ATL::CAtlExeModuleT
- ATL.CAtlExeModuleT
dev_langs:
- C++
helpviewer_keywords:
- CAtlExeModuleT class
ms.assetid: 82245f3d-91d4-44fa-aa86-7cc7fbd758d9
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 24ee6c4dfb13c31377bdd7d4f57a92d4f11ad4b8
ms.lasthandoff: 02/24/2017

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
 Abgeleitet von die Klasse `CAtlExeModuleT`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlExeModuleT::CAtlExeModuleT](#catlexemodulet)|Der Konstruktor.|  
|[CAtlExeModuleT:: ~ CAtlExeModuleT](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlExeModuleT](#initializecom)|Initialisiert die COM.|  
|[CAtlExeModuleT::ParseCommandLine](#parsecommandline)|Analysiert die Befehlszeile, und führt die Registrierung bei Bedarf.|  
|[CAtlExeModuleT::PostMessageLoop](#postmessageloop)|Diese Methode wird aufgerufen, sobald die Schleife beendet wird.|  
|[CAtlExeModuleT::PreMessageLoop](#premessageloop)|Diese Methode wird aufgerufen, unmittelbar vor die Nachrichtenschleife eingeben.|  
|[CAtlExeModuleT::RegisterClassObjects](#registerclassobjects)|Registriert das Klassenobjekt.|  
|[CAtlExeModuleT::RevokeClassObjects](#revokeclassobjects)|Hebt das Klassenobjekt.|  
|[CAtlExeModuleT::Run](#run)|Diese Methode führt Code in der EXE-Modul zu initialisieren, führen Sie die Nachrichtenschleife und bereinigen.|  
|[CAtlExeModuleT::RunMessageLoop](#runmessageloop)|Diese Methode wird die Schleife ausgeführt.|  
|[CAtlExeModuleT::UninitializeCom](#uninitializecom)|Hebt die Initialisierung COM.|  
|[CAtlExeModuleT::Unlock](#unlock)|Verringert die Sperrenanzahl des Moduls.|  
|[CAtlExeModuleT::WinMain](#winmain)|Diese Methode implementiert den Code zum Ausführen einer EXE-Datei erforderlich.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown)|Ein Flag, das angibt, dass es sollte eine Verzögerung, die das Modul heruntergefahren werden.|  
|[CAtlExeModuleT::m_dwPause](#m_dwpause)|Eine Pause-Wert verwendet, um sicherzustellen, dass alle Objekte vor dem Herunterfahren freigegeben werden.|  
|[CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout)|Ein Timeoutwert verwendet, um das Entfernen des Moduls zu verzögern.|  
  
## <a name="remarks"></a>Hinweise  
 `CAtlExeModuleT`Stellt das Modul für eine Anwendung (EXE) und enthält Code, der eine EXE-Datei erstellen, Verarbeiten der Befehlszeile, Registrieren von Klassenobjekten, die Meldungsschleife ausführt und Bereinigen von Exit unterstützt.  
  
 Diese Klasse dient zur Verbesserung der Leistung bei der COM-Objekte in der EXE-Server kontinuierlich erstellt und gelöscht werden. Nachdem der letzte COM-Objekt freigegeben wird, wartet die EXE-Datei für eine Dauer von angegebenen der [CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout) -Datenmember. Wenn während dieses Zeitraums keine Aktivität vorhanden ist (d. h. keine COM-Objekte erstellt werden), wird der Prozess des Herunterfahrens initiiert.  
  
 Die [CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown) -Datenmember ist ein Flag, das verwendet, um zu bestimmen, ob die EXE-Datei den oben definierten Mechanismus verwenden soll. Wenn sie auf "false" festgelegt ist, wird das Modul sofort beendet.  
  
 Weitere Informationen zu Modulen in ATL finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  

  
 [Von CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CAtlExeModuleT`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="a-namecatlexemoduleta--catlexemoduletcatlexemodulet"></a><a name="catlexemodulet"></a>CAtlExeModuleT::CAtlExeModuleT  
 Der Konstruktor.  
  
```
CAtlExeModuleT() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn die EXE-Modul nicht initialisiert werden konnte, wird WinMain sofort beendet, ohne weitere Verarbeitung.  
  
##  <a name="a-namedtora--catlexemoduletcatlexemodulet"></a><a name="dtor"></a>CAtlExeModuleT:: ~ CAtlExeModuleT  
 Der Destruktor.  
  
```
~CAtlExeModuleT() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordnete Ressourcen frei.  
  
##  <a name="a-nameinitializecoma--catlexemoduletinitializecom"></a><a name="initializecom"></a>CAtlExeModuleT  
 Initialisiert die COM.  
  
```
static HRESULT InitializeCom() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Konstruktor aufgerufen und kann überschrieben werden, um auf eine Weise, die sich von der Implementierung der COM-Initialisierung. Entweder die standardmäßige Implementierung ruft **CoInitializeEx (NULL, COINIT_MULTITHREADED)** oder **CoInitialize(NULL)** je nach der Konfiguration des Projekts.  
  
 Überschreiben diese Methode normalerweise erfordert überschreiben [CAtlExeModuleT::UninitializeCom](#uninitializecom).  
  
##  <a name="a-namembdelayshutdowna--catlexemoduletmbdelayshutdown"></a><a name="m_bdelayshutdown"></a>CAtlExeModuleT::m_bDelayShutdown  
 Ein Flag, das angibt, dass es sollte eine Verzögerung, die das Modul heruntergefahren werden.  
  
```
bool m_bDelayShutdown;
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter der [CAtlExeModuleT-Übersicht über](../../atl/reference/catlexemodulet-class.md) Informationen.  
  
##  <a name="a-namemdwpausea--catlexemoduletmdwpause"></a><a name="m_dwpause"></a>CAtlExeModuleT::m_dwPause  
 Eine Pause-Wert verwendet, um sicherzustellen, dass alle Objekte vor dem Herunterfahren aufgetreten sind.  
  
```
DWORD m_dwPause;
```  
  
### <a name="remarks"></a>Hinweise  
 Ändern Sie diesen Wert nach dem Aufruf von [CAtlExeModuleT](#initializecom) festlegen die Anzahl der Millisekunden, die als der Verzögerungswert für das Herunterfahren des Servers verwendet. Der Standardwert beträgt 1.000 Millisekunden.  
  
##  <a name="a-namemdwtimeouta--catlexemoduletmdwtimeout"></a><a name="m_dwtimeout"></a>CAtlExeModuleT::m_dwTimeOut  
 Ein Timeoutwert verwendet, um das Entfernen des Moduls zu verzögern.  
  
```
DWORD m_dwTimeOut;
```  
  
### <a name="remarks"></a>Hinweise  
 Ändern Sie diesen Wert nach dem Aufruf von [CAtlExeModuleT](#initializecom) definiert die Anzahl der Millisekunden, die als der Timeoutwert für das Herunterfahren des Servers verwendet. Der Standardwert ist 5000 Millisekunden. Finden Sie unter der [CAtlExeModuleT-Übersicht über](../../atl/reference/catlexemodulet-class.md) für weitere Details.  
  
##  <a name="a-nameparsecommandlinea--catlexemoduletparsecommandline"></a><a name="parsecommandline"></a>CAtlExeModuleT::ParseCommandLine  
 Analysiert die Befehlszeile, und führt die Registrierung bei Bedarf.  
  
```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpCmdLine`  
 Die Befehlszeile, die an die Anwendung übergeben werden.  
  
 `pnRetCode`  
 Das HRESULT der Registrierung (wenn es stattgefunden hat).  
  
### <a name="return-value"></a>Rückgabewert  
 Zurückgeben Sie true, wenn die Anwendung fortgesetzt werden soll, andernfalls "false" ausgeführt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, von [CAtlExeModuleT::WinMain](#winmain) und kann überschrieben werden, um Befehlszeilenoptionen zu behandeln. Die standardmäßige Implementierung überprüft **/RegServer** und **/Unregserver** Befehlszeilenargumente und führt die Registrierung bzw. Aufhebung der Registrierung durch.  
  
##  <a name="a-namepostmessageloopa--catlexemoduletpostmessageloop"></a><a name="postmessageloop"></a>CAtlExeModuleT::PostMessageLoop  
 Diese Methode wird aufgerufen, sobald die Schleife beendet wird.  
  
```
HRESULT PostMessageLoop() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um die benutzerdefinierte Anwendung Bereinigung auszuführen. Die standardmäßige Implementierung ruft [CAtlExeModuleT::RevokeClassObjects](#revokeclassobjects).  
  
##  <a name="a-namepremessageloopa--catlexemoduletpremessageloop"></a><a name="premessageloop"></a>CAtlExeModuleT::PreMessageLoop  
 Diese Methode wird aufgerufen, unmittelbar vor die Nachrichtenschleife eingeben.  
  
```
HRESULT PreMessageLoop(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nShowCmd`  
 Der Wert als die `nShowCmd` Parameter im WinMain.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um die benutzerdefinierten Initialisierungscode für die Anwendung hinzuzufügen. Die standardmäßige Implementierung registriert die Objekte der Klasse.  
  
##  <a name="a-nameregisterclassobjectsa--catlexemoduletregisterclassobjects"></a><a name="registerclassobjects"></a>CAtlExeModuleT::RegisterClassObjects  
 Das Klassenobjekt registriert mit OLE, damit andere Programme hergestellt werden können.  
  
```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *dwClsContext*  
 Gibt den Kontext, in dem das Objekt der Klasse ist, ausgeführt werden. Mögliche Werte sind CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER oder CLSCTX_LOCAL_SERVER.  
  
 `dwFlags`  
 Bestimmt, welche Verbindung auf das Klassenobjekt. Mögliche Werte sind REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE oder REGCLS_MULTI_SEPARATE.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück auf Erfolg, S_FALSE zurück, wenn es wurden keine Klassen registriert oder ein HRESULT-Fehler bei einem Fehler.  
  
##  <a name="a-namerevokeclassobjectsa--catlexemoduletrevokeclassobjects"></a><a name="revokeclassobjects"></a>CAtlExeModuleT::RevokeClassObjects  
 Entfernt das Klassenobjekt.  
  
```
HRESULT RevokeClassObjects() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück auf Erfolg, S_FALSE zurück, wenn es wurden keine Klassen registriert oder ein HRESULT-Fehler bei einem Fehler.  
  
##  <a name="a-nameruna--catlexemoduletrun"></a><a name="run"></a>CAtlExeModuleT::Run  
 Diese Methode führt Code in der EXE-Modul zu initialisieren, führen Sie die Nachrichtenschleife und bereinigen.  
  
```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nShowCmd`  
 Gibt an, wie das Fenster angezeigt werden. Dieser Parameter kann einen der Werte in erläutert die [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) Abschnitt. Der Standardwert ist SW_HIDE.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann überschrieben werden. Allerdings in der Praxis ist es besser, überschreiben [CAtlExeModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::RunMessageLoop](#runmessageloop), oder [CAtlExeModuleT::PostMessageLoop](#postmessageloop) stattdessen.  
  
##  <a name="a-namerunmessageloopa--catlexemoduletrunmessageloop"></a><a name="runmessageloop"></a>CAtlExeModuleT::RunMessageLoop  
 Diese Methode wird die Schleife ausgeführt.  
  
```
void RunMessageLoop() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann überschrieben werden, um das Verhalten der Meldungsschleife ändern.  
  
##  <a name="a-nameuninitializecoma--catlexemoduletuninitializecom"></a><a name="uninitializecom"></a>CAtlExeModuleT::UninitializeCom  
 Hebt die Initialisierung COM.  
  
```
static void UninitializeCom() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig ruft diese Methode einfach [CoUninitialize](http://msdn.microsoft.com/library/windows/desktop/ms688715) und der Destruktor aufgerufen wird. Überschreiben Sie diese Methode, wenn Sie außer Kraft setzen [CAtlExeModuleT](#initializecom).  
  
##  <a name="a-nameunlocka--catlexemoduletunlock"></a><a name="unlock"></a>CAtlExeModuleT::Unlock  
 Verringert die Sperrenanzahl des Moduls.  
  
```
LONG Unlock() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert, der möglicherweise hilfreich für die Diagnose oder testen.  
  
##  <a name="a-namewinmaina--catlexemoduletwinmain"></a><a name="winmain"></a>CAtlExeModuleT::WinMain  
 Diese Methode implementiert den Code zum Ausführen einer EXE-Datei erforderlich.  
  
```
int WinMain(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nShowCmd`  
 Gibt an, wie das Fenster angezeigt werden. Dieser Parameter kann einen der Werte in erläutert die [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) Abschnitt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die ausführbare Datei Rückgabewert zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann überschrieben werden. Wenn außer Kraft gesetzt [CAtlExeModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::PostMessageLoop](#postmessageloop), oder [CAtlExeModuleT::RunMessageLoop](#runmessageloop) nicht flexibel genug, es ist möglich, überschreiben die `WinMain` -Funktion mit dieser Methode.  
  
## <a name="see-also"></a>Siehe auch  
 [ATLDuck-Beispiel](../../visual-cpp-samples.md)   
 [CAtlModuleT-Klasse](../../atl/reference/catlmodulet-class.md)   
 [CAtlDllModuleT-Klasse](../../atl/reference/catldllmodulet-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

