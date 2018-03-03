---
title: CCommandLineInfo Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dd5f24ccf18f39ef231f19aa5b837914104b57c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
|[CCommandLineInfo::m_bShowSplash](#m_bshowsplash)|Gibt an, ob ein Begrüßungsbildschirm angezeigt werden sollen.|  
|[CCommandLineInfo::m_nShellCommand](#m_nshellcommand)|Gibt an die Shell-Befehl verarbeitet werden.|  
|[CCommandLineInfo::m_strDriverName](#m_strdrivername)|Gibt an, den Treiber benennen, ist der Shellbefehl Print, andernfalls leer.|  
|[CCommandLineInfo::m_strFileName](#m_strfilename)|Gibt an, der Dateiname, der geöffnet oder gedruckt werden. leer, wenn der Shellbefehl neu "oder" DDE ist.|  
|[CCommandLineInfo::m_strPortName](#m_strportname)|Gibt den Port an benennen, ist der Shellbefehl Print, andernfalls leer.|  
|[CCommandLineInfo::m_strPrinterName](#m_strprintername)|Gibt an, den Drucker benennen, ist der Shellbefehl Print, andernfalls leer.|  
|[CCommandLineInfo::m_strRestartIdentifier](#m_strrestartidentifier)|Gibt der Neustart des eindeutigen Bezeichner für den Neustart-Manager an, wenn die Anwendung für der Neustart-Manager neu gestartet.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen eine MFC-Anwendung in der Regel eine lokale Instanz dieser Klasse in der [InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) Funktion seines Application-Objekts. Dieses Objekt wird dann an übergeben [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline), wiederholt aufgerufen [ParseParam](#parseparam) zum Ausfüllen der `CCommandLineInfo` Objekt. Die `CCommandLineInfo` Objekt wird dann zum übergeben [CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand) , behandeln die Befehlszeilenargumente und Flags.  
  
 Dieses Objekt können die folgenden Befehlszeilenoptionen und Parameter gekapselt werden:  
  
|Befehlszeilenargument|Ausgeführter Befehl|  
|----------------------------|----------------------|  
|*app*|Neue Datei.|  
|*App* Dateiname|Um die Datei zu öffnen.|  
|*App* `/p` Dateiname|Drucken Sie Datei auf dem Standarddrucker.|  
|*App* `/pt` Filename-Druckeranschluss-Treiber|Datei mit dem angegebenen Drucker zu drucken.|  
|*App*`/dde`|Starten und "await" DDE-Befehl.|  
|*App*`/Automation`|Als OLE-Automatisierungsserver starten.|  
|*App*`/Embedding`|Starten Sie zum Bearbeiten von eines eingebetteten OLE-Elements.|  
|*App*`/Register`<br /><br /> *App*`/Regserver`|Informiert die Anwendung Registrierungsaufgaben ausführen.|  
|*App*`/Unregister`<br /><br /> *App*`/Unregserver`|Informiert die Anwendung alle Aufgaben für die Aufhebung der Registrierung ausgeführt.|  
  
 Leiten Sie eine neue Klasse von `CCommandLineInfo` anderen Flags und Parameterwerte zu behandeln. Überschreiben Sie [ParseParam](#parseparam) , die neuen Flags zu behandeln.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CCommandLineInfo`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="ccommandlineinfo"></a>CCommandLineInfo::CCommandLineInfo  
 Dieser Konstruktor erstellt ein `CCommandLineInfo` Objekt mit Standardwerten.  
  
```  
CCommandLineInfo();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Standardeinstellung ist, um den Begrüßungsbildschirm anzuzeigen ( `m_bShowSplash=TRUE`) und den neuen Befehl im Menü Datei auszuführen ( `m_nShellCommand` **= NewFile**).  
  
 Ruft die Anwendung-Framework [ParseParam](#parseparam) Datenmember dieses Objekts zu füllen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#54](../../mfc/codesnippet/cpp/ccommandlineinfo-class_1.cpp)]  
  
##  <a name="m_brunautomated"></a>CCommandLineInfo::m_bRunAutomated  
 Gibt an, dass die `/Automation` Flag wurde in der Befehlszeile gefunden.  
  
```  
BOOL m_bRunAutomated;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `TRUE`, dies bedeutet, dass Sie als OLE-Automatisierungsserver gestartet.  
  
##  <a name="m_brunembedded"></a>CCommandLineInfo::m_bRunEmbedded  
 Gibt an, dass die `/Embedding` Flag wurde in der Befehlszeile gefunden.  
  
```  
BOOL m_bRunEmbedded;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `TRUE`, dies bedeutet, dass für die Bearbeitung von eines eingebetteten OLE-Elements gestartet.  
  
##  <a name="m_bshowsplash"></a>CCommandLineInfo::m_bShowSplash  
 Gibt an, dass der Begrüßungsbildschirm angezeigt werden soll.  
  
```  
BOOL m_bShowSplash;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `TRUE`, dies bedeutet, dass den Begrüßungsbildschirm für diese Anwendung beim Start angezeigt werden soll. Die standardmäßige Implementierung des [ParseParam](#parseparam) wird dieses Datenelement auf `TRUE` Wenn [M_nShellCommand](#m_nshellcommand) gleich `CCommandLineInfo::FileNew`.  
  
##  <a name="m_nshellcommand"></a>CCommandLineInfo::m_nShellCommand  
 Gibt die Shellbefehl für diese Instanz der Anwendung an.  
  
```  
m_nShellCommand;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ für dieses Datenelement ist den folgenden enumerierten Typ, definiert in der `CCommandLineInfo` Klasse.  
  
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
  
 Eine kurze Beschreibung der folgenden Werte sind finden Sie in der folgenden Liste.  
  
- `CCommandLineInfo::FileNew`Gibt an, dass kein Dateiname in der Befehlszeile gefunden wurde.  
  
- `CCommandLineInfo::FileOpen`Gibt an, dass ein Dateiname in der Befehlszeile gefunden wurde und dass keines der folgenden Flags in der Befehlszeile gefunden wurden: `/p`, `/pt`, `/dde`.  
  
- `CCommandLineInfo::FilePrint`Gibt an, dass die `/p` Flag wurde in der Befehlszeile gefunden.  
  
- `CCommandLineInfo::FilePrintTo`Gibt an, dass die `/pt` Flag wurde in der Befehlszeile gefunden.  
  
- `CCommandLineInfo::FileDDE`Gibt an, dass die `/dde` Flag wurde in der Befehlszeile gefunden.  
  
- `CCommandLineInfo::AppRegister`Gibt an, dass die `/Register` oder `/Regserver` Flag wurde gefunden, in der Befehlszeile und die Anwendung wurde aufgefordert, zu registrieren.  
  
- `CCommandLineInfo::AppUnregister`Gibt an, dass die `/Unregister` oder `/Unregserver` Anwendung wurde beim Aufheben der Registrierung aufgefordert.  
  
- `CCommandLineInfo::RestartByRestartManager`Gibt an, dass die Anwendung vom Neustart-Manager neu gestartet wurde.  
  
- `CCommandLineInfo::FileNothing`Deaktiviert die Anzeige einer neuen untergeordneten MDI-Fensters auf Start. Programmbedingt anzeigen Anwendungs-Assistenten generierte MDI-Anwendungen ein neues untergeordnetes Fenster beim Start. Um dieses Feature deaktivieren, können Sie eine Anwendung `CCommandLineInfo::FileNothing` wie beim Aufrufen der Shellbefehl [ProcessShellCommand ein](../../mfc/reference/cwinapp-class.md#processshellcommand). `ProcessShellCommand`wird aufgerufen, indem Sie die `InitInstance( )` aller `CWinApp` abgeleitete Klassen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#55](../../mfc/codesnippet/cpp/ccommandlineinfo-class_2.cpp)]  
  
##  <a name="m_strdrivername"></a>CCommandLineInfo::m_strDriverName  
 Speichert den Wert des dritten Parameters der nicht-Flag in der Befehlszeile an.  
  
```  
CString m_strDriverName;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Parameter ist in der Regel der Name des Druckertreibers für einen Druckserver auf Shell-Befehl. Die standardmäßige Implementierung des [ParseParam](#parseparam) legt diesen Datenmember nur, wenn die `/pt` Flag wurde in der Befehlszeile gefunden.  
  
##  <a name="m_strfilename"></a>CCommandLineInfo::m_strFileName  
 Speichert den Wert des ersten Parameters nicht-Flag in der Befehlszeile an.  
  
```  
CString m_strFileName;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Parameter ist in der Regel der Name der Datei zu öffnen.  
  
##  <a name="m_strportname"></a>CCommandLineInfo::m_strPortName  
 Speichert den Wert des vierten Parameters der nicht-Flag in der Befehlszeile an.  
  
```  
CString m_strPortName;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Parameter ist in der Regel den Namen des Druckeranschlusses für einen Druckserver auf Shell-Befehl. Die standardmäßige Implementierung des [ParseParam](#parseparam) legt diesen Datenmember nur, wenn die `/pt` Flag wurde in der Befehlszeile gefunden.  
  
##  <a name="m_strprintername"></a>CCommandLineInfo::m_strPrinterName  
 Speichert den Wert des zweiten Parameters nicht-Flag in der Befehlszeile an.  
  
```  
CString m_strPrinterName;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Parameter ist in der Regel der Name des Druckers für einen Druckserver auf Shell-Befehl. Die standardmäßige Implementierung des [ParseParam](#parseparam) legt diesen Datenmember nur, wenn die `/pt` Flag wurde in der Befehlszeile gefunden.  
  
##  <a name="m_strrestartidentifier"></a>CCommandLineInfo::m_strRestartIdentifier  
 Der eindeutige Neustart Bezeichner in der Befehlszeile angegeben.  
  
```  
CString m_strRestartIdentifier;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Neustart-Bezeichner ist eindeutig für jede Instanz der Anwendung.  
  
 Wenn der Neustart-Manager die Anwendung beendet und um den Neustart konfiguriert wird, führt der Neustart-Manager die Anwendung über die Befehlszeile mit dem Neustart-Bezeichner als optionalen Parameter an. Wenn der Neustart-Manager den Neustart-Bezeichner verwendet wird, kann die Anwendung zuvor geöffneten Dokumente öffnen und Wiederherstellen automatisch gespeicherte Dateien.  
  
##  <a name="parseparam"></a>CCommandLineInfo::ParseParam  
 Das Framework ruft diese Funktion, um die Analyse/einzelner Parameter über die Befehlszeile zu interpretieren. Die zweite Version unterscheidet sich von der ersten nur in Unicode-Projekten.  
  
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
 `pszParam`  
 Der Parameter oder ein Flag.  
  
 *bFlag*  
 Gibt an, ob `pszParam` ist ein Parameter oder ein Flag.  
  
 `bLast`  
 Gibt an, ob dies der letzte Parameter oder -Flag in der Befehlszeile angegeben ist.  
  
### <a name="remarks"></a>Hinweise  
 [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline) Aufrufe `ParseParam` einmal für jeden Parameter oder ein Flag in der Befehlszeile, um als Argument übergeben `pszParam`. Wenn das erste Zeichen des Parameters ist eine "  **-** "oder"  **/** ", wird es entfernt wird und *bFlag* auf festgelegt ist `TRUE`. Beim Analysieren des letzten Parameters, `bLast` festgelegt ist, um `TRUE`.  
  
 Die standardmäßige Implementierung dieser Funktion erkennt die folgenden Flags: `/p`, `/pt`, `/dde`, `/Automation`, und `/Embedding`, wie in der folgenden Tabelle dargestellt:  
  
|Befehlszeilenargument|Ausgeführter Befehl|  
|----------------------------|----------------------|  
|*app*|Neue Datei.|  
|*App* Dateiname|Um die Datei zu öffnen.|  
|*App* `/p` Dateiname|Drucken Sie Datei auf dem Standarddrucker.|  
|*App* `/pt` Filename-Druckeranschluss-Treiber|Datei mit dem angegebenen Drucker zu drucken.|  
|*App*`/dde`|Starten und "await" DDE-Befehl.|  
|*App*`/Automation`|Als OLE-Automatisierungsserver starten.|  
|*App*`/Embedding`|Starten Sie zum Bearbeiten von eines eingebetteten OLE-Elements.|  
|*App*`/Register`<br /><br /> *App*`/Regserver`|Informiert die Anwendung Registrierungsaufgaben ausführen.|  
|*App*`/Unregister`<br /><br /> *App*`/Unregserver`|Informiert die Anwendung alle Aufgaben für die Aufhebung der Registrierung ausgeführt.|  
  
 Diese Informationen werden gespeichert, [M_bRunAutomated](#m_brunautomated), [M_bRunEmbedded](#m_brunembedded), und [M_nShellCommand](#m_nshellcommand). Flags werden entweder durch einen Schrägstrich markiert "  **/** 'oder Bindestrich'  **-** ".  
  
 Die standardmäßige Implementierung setzt den ersten nicht-Flag-Parameter in [M_strFileName](#m_strfilename). Im Fall von der `/pt` Flag die standardmäßige Implementierung setzt den zweiten, dritten und vierten nicht Flag-Parameter in [M_strPrinterName](#m_strprintername), [M_strDriverName](#m_strdrivername), und [M_ StrPortName](#m_strportname)zugeordnet.  
  
 Die standardmäßige Implementierung setzt auch [M_bShowSplash](#m_bshowsplash) auf `TRUE` nur bei einer neuen Datei. Bei einer neuen Datei hat der Benutzer die Aktion, die im Zusammenhang mit der Anwendung selbst übernommen. In allen anderen Fällen, z. B. Öffnen von vorhandenen Dateien mithilfe der Befehlsshell umfasst die Benutzeraktion die Datei direkt aus. In einer Sicht der dokumentorientierte muss der Begrüßungsbildschirm nicht angekündigt werden, die Anwendung gestartet.  
  
 Überschreiben Sie diese Funktion in der abgeleiteten Klasse anderen Flag und Parameter-Werte behandelt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline)   
 [CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)

