---
title: Klasse CCommandLineInfo | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- CCommandLineInfo class
- command line, parsing
- parsing, command-line arguments
- argv argument
- startup code, parsing command-line arguments
- application flags [C++]
ms.assetid: 3e313ddb-0a82-4991-87ac-a27feff4668c
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: cb8cd58e4e7cf0318b8826cf473739e26e730273
ms.lasthandoff: 02/24/2017

---
# <a name="ccommandlineinfo-class"></a>CCommandLineInfo-Klasse
Unterstützt die Analyse der Befehlszeile beim Anwendungsstart.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CCommandLineInfo : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCommandLineInfo::CCommandLineInfo](#ccommandlineinfo)|Erstellt ein standardmäßiges `CCommandLineInfo` Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCommandLineInfo::ParseParam](#parseparam)|Überschreiben Sie diesen Rückruf zum Analysieren der einzelnen Parameter.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCommandLineInfo::m_bRunAutomated](#m_brunautomated)|Gibt die Befehlszeile an **/Automation** Option wurde gefunden.|  
|[CCommandLineInfo::m_bRunEmbedded](#m_brunembedded)|Gibt die Befehlszeile an **/einbetten** Option wurde gefunden.|  
|[CCommandLineInfo::m_bShowSplash](#m_bshowsplash)|Gibt an, ob ein Begrüßungsbildschirm angezeigt werden soll.|  
|[CCommandLineInfo::m_nShellCommand](#m_nshellcommand)|Gibt den Befehl "Shell" verarbeitet werden.|  
|[CCommandLineInfo::m_strDriverName](#m_strdrivername)|Den Treiber gibt name ist der Shellbefehl drucken bis; andernfalls leer.|  
|[CCommandLineInfo::m_strFileName](#m_strfilename)|Gibt den Dateinamen geöffnet oder gedruckt werden sollen. leer, wenn die Shellbefehl neu oder DDE.|  
|[CCommandLineInfo::m_strPortName](#m_strportname)|Gibt den Port name ist der Shellbefehl drucken bis; andernfalls leer.|  
|[CCommandLineInfo::m_strPrinterName](#m_strprintername)|Gibt an, den Drucker benennen, ist von der Shellbefehl drucken bis; andernfalls leer.|  
|[CCommandLineInfo::m_strRestartIdentifier](#m_strrestartidentifier)|Gibt den eindeutigen Neustart-Bezeichner für den Neustart-Manager an, wenn der Neustart-Manager die Anwendung neu gestartet.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen eine MFC-Anwendung in der Regel eine lokale Instanz dieser Klasse in der [InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) Funktion des Application-Objekts. Dieses Objekt wird dann an übergeben [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline), die wiederholt aufruft [ParseParam](#parseparam) zum Ausfüllen der `CCommandLineInfo` Objekt. Die `CCommandLineInfo` Objekt wird dann an übergeben [CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand) die Befehlszeilenargumente und Flags zu behandeln.  
  
 Dieses Objekt können Sie um die folgenden Befehlszeilenoptionen und Parameter zu kapseln:  
  
|Befehlszeilenargument|Ausgeführter Befehl|  
|----------------------------|----------------------|  
|*app*|Neue Datei.|  
|*App* Dateiname|Um die Datei zu öffnen.|  
|*App* **/p** Dateiname|Drucken Sie Datei auf dem Standarddrucker.|  
|*App* **/pt** Dateiname Druckeranschluss-Treiber|Datei auf dem angegebenen Drucker zu drucken.|  
|*app* **/dde**|Starten und "await" DDE-Befehl.|  
|*App*  ** /Automatisierung**|Als OLE-Automatisierungsserver starten.|  
|*App* **/ einbetten**|Starten Sie ein eingebettetes OLE-Element zu bearbeiten.|  
|*App*  ** /registrieren**<br /><br /> *App*  ** /regserver**|Informiert die Anwendung alle Registrierungsaufgaben durchführen.|  
|*App* **/ Unregister**<br /><br /> *App*  ** /Unregserver**|Informiert die Anwendung alle Aufgaben für die Aufhebung der Registrierung durchführen.|  
  
 Leiten Sie eine neue Klasse von `CCommandLineInfo` , andere Flags und Parameterwerte zu behandeln. Überschreiben Sie [ParseParam](#parseparam) die neuen Flags zu behandeln.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CCommandLineInfo`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="ccommandlineinfo"></a>CCommandLineInfo::CCommandLineInfo  
 Dieser Konstruktor erstellt ein `CCommandLineInfo` -Objekt mit Standardwerten.  
  
```  
CCommandLineInfo();
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird der Begrüßungsbildschirm angezeigt ( `m_bShowSplash` **= TRUE**) und im Menü Datei den neuen Befehl auszuführen ( `m_nShellCommand` **= New File**).  
  
 Die Anwendung Framework ruft [ParseParam](#parseparam) -Datenmember des Objekts zu füllen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#54;](../../mfc/codesnippet/cpp/ccommandlineinfo-class_1.cpp)]  
  
##  <a name="m_brunautomated"></a>CCommandLineInfo::m_bRunAutomated  
 Gibt an, dass die **/Automation** Flag wurde in der Befehlszeile gefunden.  
  
```  
BOOL m_bRunAutomated;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn **TRUE**, bedeutet das, dass als OLE-Automatisierungsserver gestartet.  
  
##  <a name="m_brunembedded"></a>CCommandLineInfo::m_bRunEmbedded  
 Gibt an, dass die **/einbetten** Flag wurde in der Befehlszeile gefunden.  
  
```  
BOOL m_bRunEmbedded;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn **TRUE**, dies bedeutet, dass Sie für die Bearbeitung von eines eingebetteten OLE-Elements starten.  
  
##  <a name="m_bshowsplash"></a>CCommandLineInfo::m_bShowSplash  
 Gibt an, dass der Begrüßungsbildschirm angezeigt werden soll.  
  
```  
BOOL m_bShowSplash;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn **TRUE**, dies bedeutet, dass den Begrüßungsbildschirm für diese Anwendung beim Start angezeigt werden soll. Die standardmäßige Implementierung des [ParseParam](#parseparam) wird dieses Datenelement auf **TRUE** Wenn [M_nShellCommand](#m_nshellcommand) gleich **CCommandLineInfo::FileNew**.  
  
##  <a name="m_nshellcommand"></a>CCommandLineInfo::m_nShellCommand  
 Gibt den Befehl "Shell" für diese Instanz der Anwendung an.  
  
```  
m_nShellCommand;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ für dieses Datenelement ist den folgenden Aufzählungstyp, definiert in der `CCommandLineInfo` Klasse.  
  
 `enum{`  
  
 `FileNew,`  
  
 `FileOpen,`  
  
 `FilePrint,`  
  
 `FilePrintTo,`  
  
 `FileDDE,`  
  
 `AppRegister,`  
  
 `AppUnregister,`  
  
 `RestartByRestartManager,`  
  
 `FileNothing = -1`  
  
 `};`  
  
 Eine kurze Beschreibung dieser Werte finden Sie in der folgenden Liste.  
  
- `CCommandLineInfo::FileNew`Gibt an, dass kein Dateiname in der Befehlszeile gefunden wurde.  
  
- `CCommandLineInfo::FileOpen`Gibt an, dass ein Dateiname in der Befehlszeile gefunden wurde und keine der folgenden Flags in der Befehlszeile gefunden wurden: `/p`, `/pt`, `/dde`.  
  
- `CCommandLineInfo::FilePrint`Gibt an, dass die `/p` Flag wurde in der Befehlszeile gefunden.  
  
- `CCommandLineInfo::FilePrintTo`Gibt an, dass die `/pt` Flag wurde in der Befehlszeile gefunden.  
  
- `CCommandLineInfo::FileDDE`Gibt an, dass die `/dde` Flag wurde in der Befehlszeile gefunden.  
  
- `CCommandLineInfo::AppRegister`Gibt an, dass die `/Register` oder `/Regserver` Kennzeichen in der Befehlszeile gefunden wurde und die Anwendung wurde aufgefordert, zu registrieren.  
  
- `CCommandLineInfo::AppUnregister`Gibt an, dass die `/Unregister` oder `/Unregserver` Anwendung wurde beim Aufheben der Registrierung aufgefordert.  
  
- `CCommandLineInfo::RestartByRestartManager`Gibt an, dass die Anwendung vom Neustart-Manager neu gestartet wurde.  
  
- `CCommandLineInfo::FileNothing`Schaltet die Anzeige einer neuen untergeordneten MDI-Fensters auf Start. Standardmäßig anzeigen MDI-Anwendung vom Assistenten generierte Anwendung ein neues untergeordnetes Fenster beim Start. Um dieses Feature zu deaktivieren, können Sie eine Anwendung `CCommandLineInfo::FileNothing` wie beim Aufrufen der Shellbefehl [ProcessShellCommand ein](../../mfc/reference/cwinapp-class.md#processshellcommand). `ProcessShellCommand`wird aufgerufen, indem die `InitInstance( )` aller `CWinApp` abgeleiteten Klassen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#55;](../../mfc/codesnippet/cpp/ccommandlineinfo-class_2.cpp)]  
  
##  <a name="m_strdrivername"></a>CCommandLineInfo::m_strDriverName  
 Speichert den Wert des dritten Parameters nicht-Flag in der Befehlszeile.  
  
```  
CString m_strDriverName;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Parameter ist in der Regel den Namen des Druckertreibers für einen Druckserver, Shell-Befehl. Die standardmäßige Implementierung des [ParseParam](#parseparam) legt diese Datenmember nur, wenn die **/pt** Flag wurde in der Befehlszeile gefunden.  
  
##  <a name="m_strfilename"></a>CCommandLineInfo::m_strFileName  
 Speichert den Wert des ersten Parameters nicht-Flag in der Befehlszeile.  
  
```  
CString m_strFileName;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Parameter ist in der Regel der Name der zu öffnenden Datei.  
  
##  <a name="m_strportname"></a>CCommandLineInfo::m_strPortName  
 Speichert den Wert der vierten Parameter von nicht-Flag in der Befehlszeile an.  
  
```  
CString m_strPortName;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Parameter ist in der Regel den Namen des Ports für einen Druckserver, Shell-Befehl. Die standardmäßige Implementierung des [ParseParam](#parseparam) legt diese Datenmember nur, wenn die **/pt** Flag wurde in der Befehlszeile gefunden.  
  
##  <a name="m_strprintername"></a>CCommandLineInfo::m_strPrinterName  
 Speichert den Wert des zweiten Parameters nicht-Flag in der Befehlszeile.  
  
```  
CString m_strPrinterName;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Parameter ist in der Regel der Name des Druckers für einen Druckserver, Shell-Befehl. Die standardmäßige Implementierung des [ParseParam](#parseparam) legt diese Datenmember nur, wenn die **/pt** Flag wurde in der Befehlszeile gefunden.  
  
##  <a name="m_strrestartidentifier"></a>CCommandLineInfo::m_strRestartIdentifier  
 Der eindeutige neu Bezeichner in der Befehlszeile starten.  
  
```  
CString m_strRestartIdentifier;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Neustart-Bezeichner ist eindeutig für jede Instanz der Anwendung.  
  
 Wenn der Neustart-Manager die Anwendung beendet und so konfiguriert ist, dass es neu starten, führt der Neustart-Manager die Anwendung über die Befehlszeile mit dem Neustart Bezeichner als optionalen Parameter an. Wenn der Neustart-Manager den Neustart-Bezeichner verwendet wird, kann die Anwendung zuvor geöffneten Dokumente öffnen und automatisch gespeicherte Dateien wiederherstellen.  
  
##  <a name="parseparam"></a>CCommandLineInfo::ParseParam  
 Das Framework ruft diese Funktion, um die Analyse/interpretieren einzelne Parameter von der Befehlszeile aus. Die zweite Version unterscheidet sich von der ersten nur in Unicode-Projekten.  
  
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
 Gibt an, ob dies der letzte Parameter oder -Flag in der Befehlszeile.  
  
### <a name="remarks"></a>Hinweise  
 [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline) Aufrufe `ParseParam` einmal für jeden Parameter oder ein Flag in der Befehlszeile, um als Argument übergeben `pszParam`. Wenn das erste Zeichen des Parameters ist ein " ** - **'oder' ** / **", wird es entfernt und *bFlag* auf festgelegt ist **TRUE**. Beim Analysieren des letzten Parameters, `bLast` Wert **TRUE**.  
  
 Die standardmäßige Implementierung dieser Funktion erkennt die folgenden Flags: **/p**, **/pt**, **DDE**, **/Automation**, und **/einbetten**, wie in der folgenden Tabelle dargestellt:  
  
|Befehlszeilenargument|Ausgeführter Befehl|  
|----------------------------|----------------------|  
|*app*|Neue Datei.|  
|*App* Dateiname|Um die Datei zu öffnen.|  
|*App* **/p** Dateiname|Drucken Sie Datei auf dem Standarddrucker.|  
|*App* **/pt** Dateiname Druckeranschluss-Treiber|Datei auf dem angegebenen Drucker zu drucken.|  
|*app* **/dde**|Starten und "await" DDE-Befehl.|  
|*App*  ** /Automatisierung**|Als OLE-Automatisierungsserver starten.|  
|*App* **/ einbetten**|Starten Sie ein eingebettetes OLE-Element zu bearbeiten.|  
|*App*  ** /registrieren**<br /><br /> *App*  ** /regserver**|Informiert die Anwendung alle Registrierungsaufgaben durchführen.|  
|*App* **/ Unregister**<br /><br /> *App*  ** /Unregserver**|Informiert die Anwendung alle Aufgaben für die Aufhebung der Registrierung durchführen.|  
  
 Diese Informationen werden gespeichert [M_bRunAutomated](#m_brunautomated), [M_bRunEmbedded](#m_brunembedded), und [M_nShellCommand](#m_nshellcommand). Flags werden entweder durch einen Schrägstrich gekennzeichnet ' ** / **'oder Bindestrich' ** - **".  
  
 Die standardmäßige Implementierung legt den ersten nicht-Flag-Parameter in [M_strFileName](#m_strfilename). Im Fall von der **/pt** Flag die standardmäßige Implementierung setzt den zweiten, dritten und vierten nicht-Flag-Parameter in [M_strPrinterName](#m_strprintername), [M_strDriverName](#m_strdrivername), und [M_strPortName](#m_strportname)bzw..  
  
 Außerdem wird die Implementierung der [M_bShowSplash](#m_bshowsplash) auf **TRUE** nur bei einer neuen Datei. Bei einer neuen Datei hat der Benutzer im Zusammenhang mit der Anwendung selbst Aktion. In allen anderen Fällen, z. B. Öffnen von vorhandenen Dateien mit der Shell umfasst die Benutzeraktion die Datei direkt aus. In Standpunkt dokumentorientierte muss der Begrüßungsbildschirm nicht zu die Anwendung starten können.  
  
 Überschreiben Sie diese Funktion in der abgeleiteten Klasse anderen Kennzeichen und Parameter-Werte behandelt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline)   
 [CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)


