---
title: "Leitfaden zum Portieren: COM Spy | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 24aa0d52-4014-4acb-8052-f4e2e4bbc3bb
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Leitfaden zum Portieren: COM Spy
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieses Thema ist das zweite aus einer Reihe von Artikeln, die die Aktualisierung älterer Visual C\+\+\-Projekte auf die neueste Version von Visual Studio veranschaulichen.  Der Beispielcode in diesem Thema wurde zuletzt mit Visual Studio 2005 kompiliert.  
  
## COMSpy  
 COMSpy ist ein Programm, das die Aktivität von Serviced Components auf einem Computer überwacht und protokolliert.  Serviced Components sind COM\+\-Komponenten, die auf einem System ausgeführt werden und von Computern im selben Netzwerk verwendet werden können.  Sie werden durch die Funktion „Komponentendienste“ in der Windows\-Systemsteuerung verwaltet.  
  
### Schritt 1.Konvertieren der Projektdatei  
 Die Projektdatei lässt sich problemlos konvertieren und erstellt einen Migrationsbericht.  Einige Einträge in dem Bericht geben Hinweise auf Probleme, die eventuell beseitigt werden müssen.  Im Folgenden eines der gemeldeten Probleme. Beachten Sie, dass Fehlermeldungen in diesem Thema zur besseren Lesbarkeit manchmal gekürzt werden; z. B. werden die vollständigen Pfade teilweise entfernt.  
  
  **ComSpyAudit\\ComSpyAudit.vcproj: MSB8012: $\(TargetPath\) \(„C:\\Users\\Benutzername\\Desktop\\spy\\spy\\ComSpyAudit\\.  \\XP32\_DEBUG\\ComSpyAudit.dll“\) entspricht nicht dem OutputFile\-Eigenschaftswert des Bibliothekars „.  \\XP32\_DEBUG\\ComSpyAudit.dll“ \(„C:\\Users\\Benutzername\\Desktop\\spy\\spy\\XP32\_DEBUG\\ComSpyAudit.dll“\) in der Projektkonfiguration „Unicode Debug&#124;Win32“.  Das Projekt wird daher möglicherweise nicht ordnungsgemäß erstellt.  Um dieses Problem zu beheben, stellen Sie sicher, dass der Eigenschaftswert $\(TargetPath\) mit dem in %\(Lib.OutputFile\) angegebenen Wert übereinstimmt.**  Ein häufiges Problem beim Upgrade von Projekten besteht darin, dass die Linker\-OutputFile\-Einstellung im Dialogfeld „Projekteigenschaften“ eventuell überprüft werden muss.  Bei Projekten vor Visual Studio 2010 ist OutputFile eine Einstellung, die dem Assistenten für die automatische Konvertierung Probleme bereitet, wenn sie nicht auf einen Standardwert festgelegt ist.  In diesem Fall wurden die Pfade für die Ausgabedateien auf den nicht standardmäßigen Ordner XP32\_DEBUG festgelegt.  Weitere Informationen zu diesem Fehler haben wir in einem [Blogbeitrag](http://blogs.msdn.com/b/vcblog/archive/2010/03/02/visual-studio-2010-c-project-upgrade-guide.aspx) zum Visual C\+\+ 2010\-Projektupgrade gefunden, einem Upgrade, bei dem der wichtige Wechsel von vcbuild zu msbuild unternommen wurde.  Gemäß den Informationen in diesem Blogbeitrag lautet der Standardwert für die OutputFile\-Einstellung beim Erstellen eines neuen Projekts $\(OutDir\)$\(TargetName\)$\(TargetExt\), doch wird dieser Wert nicht bei der Konvertierung festgelegt, da die Überprüfung der Richtigkeit für konvertierte Projekte nicht möglich ist.  Wir prüfen nun trotzdem, ob dies für OutputFile möglich ist.  Es funktioniert und wir können den Vorgang fortsetzen.  Wenn es keinen bestimmten Grund für die Verwendung eines nicht dem Standard entsprechenden Ausgabeordners gibt, wird die Verwendung des standardmäßigen Speicherorts empfohlen.  In diesem Fall haben wir als Ausgabespeicherort während der Portierung und Aktualisierung den nicht standardmäßigen Speicherort belassen. $\(OutDir\) wird in der Debugkonfiguration in den XP32\_DEBUG\-Ordner und in der Releasekonfiguration in den ReleaseU\-Ordner aufgelöst.  
  
### Schritt 2Erstellen des Projekts  
 Beim Erstellen des portierten Projekts treten eine Reihe von Fehlern und Warnungen auf.  
  
 ComSpyCtl wird aufgrund des folgenden Fehlers nicht kompiliert:  
  
  **atlcom.h\(611\): Fehler C2664: „HRESULT CComSpy::IPersistStreamInit\_Save\(LPSTREAM,BOOL,ATL::ATL\_PROPMAP\_ENTRY \*\)“: Konvertierung von Argument 3 von „const ATL::ATL\_PROPMAP\_ENTRY \*“ in „ATL::ATL\_PROPMAP\_ENTRY \*“ nicht möglich.**  
**atlcom.h\(611\): Hinweis: Durch die Konvertierung gehen Qualifizierer verloren.**  
**atlcom.h\(608\): Hinweis: Bei der Kompilierung der Memberfunktion der Klassenvorlage „HRESULT ATL::IPersistStreamInitImpl\<CComSpy\>::Save\(LPSTREAM,BOOL\)“**  
**\\spy\\spy\\comspyctl\\ccomspy.h\(28\): Hinweis: Siehe Verweis auf die kompilierte Klassenvorlageninstanziierung „ATL::IPersistStreamInitImpl\<CComSpy\>“** Die Fehlermeldung verweist auf die Save\-Methode für die Klasse IPersistStreamInitImpl in atlcom.h.  
  
```  
STDMETHOD(Save)(_Inout_ LPSTREAM pStm, _In_ BOOL fClearDirty)  
{  
T* pT = static_cast<T*>(this);  
ATLTRACE(atlTraceCOM, 2, _T("IPersistStreamInitImpl::Save\n"));  
return pT->IPersistStreamInit_Save(pStm, fClearDirty, T::GetPropertyMap());  
}  
```  
  
 Das Problem besteht darin, dass eine Konvertierung, die von einer älteren Version des Compilers akzeptiert wurde, nicht mehr gültig ist.  Um dem C\+\+\-Standard zu entsprechen, wird zuvor zulässiger Code nicht mehr zugelassen.  In diesem Fall ist es nicht sicher, einen nicht konstanten Zeiger an eine Funktion zu übergeben, die einen konstanten Zeiger erwartet.  Die Lösung besteht darin, die Deklaration von IPersistStreamInit\_Save in der CComSpy\-Klasse zu suchen und den const\-Modifizierer zu dem dritten Parameter hinzuzufügen.  
  
```  
HRESULT CComSpy::IPersistStreamInit_Save(LPSTREAM pStm, BOOL /* fClearDirty */, const ATL_PROPMAP_ENTRY* pMap)  
  
```  
  
 Eine ähnliche Änderung wird an IPersistStreamInit\_Load vorgenommen.  
  
```  
HRESULT IPersistStreamInit_Load(LPSTREAM pStm, const ATL_PROPMAP_ENTRY* pMap);  
```  
  
 Der nächste Fehler befasst sich mit der Registrierung.  
  
  **Fehler MSB3073: Der Befehl „regsvr32 \/s \/c ‚C:\\Users\\Benutzername\\Desktop\\spy\\spy\\ComSpyCtl\\.  \\XP32\_DEBUG\\ComSpyCtl.lib‘**  
**Fehler MSB3073: Echo regsvr32 Ausführungszeit   \> „.  \\XP32\_DEBUG\\regsvr32.trg“**  
**Fehler MSB3073:**  
**Fehler MSB3073: :VCEnd" wurde mit dem Code 3 beendet.**  Dieser Postbuild\-Registrierungsbefehl wird nicht mehr benötigt.  Stattdessen wird einfach der benutzerdefinierte Befehl entfernt und in den Linker\-Einstellungen angegeben, um die Ausgabe zu registrieren.  
  
### Umgang mit Warnungen  
 Das Projekt erzeugt die folgende Linkerwarnung.  
  
  **Warnung LNK4075: Ignoriere „\/EDITANDCONTINUE“ aufgrund der „\/SAFESEH“\-Spezifikation** Die Compileroption \/SAFESEH ist im Debugmodus nicht geeignet. Hier ist \/EDITANDCONTINUE nützlich; die Lösung besteht also darin, \/SAFESEH ausschließlich für Debugkonfigurationen zu deaktivieren.  Dazu wird das Eigenschaftendialogfeld des Projekts geöffnet, das den Fehler produziert, und zuerst die Konfiguration auf Debuggen \(Debug Unicode\) festgelegt. Danach wird im Abschnitt „Erweitert“ die Eigenschaft „Image weist sichere Ausnahmehandler auf“ auf „Nein“ zurückgesetzt \(\/SAFESEH:NO\).  
  
 Der Compiler warnt uns davor, dass PROP\_ENTRY\_EX veraltet ist.  Es ist nicht sicher und der empfohlene Ersatz ist PROP\_ENTRY\_TYPE\_EX.  
  
```  
BEGIN_PROPERTY_MAP(CComSpy)  
PROP_ENTRY_EX( "LogFile", DISPID_LOGFILE, CLSID_ComSpyPropPage, IID_IComSpy)  
PROP_ENTRY_EX( "ShowGridLines", DISPID_GRIDLINES, CLSID_ComSpyPropPage, IID_IComSpy)  
PROP_ENTRY_EX( "Audit", DISPID_AUDIT, CLSID_ComSpyPropPage, IID_IComSpy)  
PROP_ENTRY_EX( "ColWidth", DISPID_COLWIDTH, CLSID_ComSpyPropPage, IID_IComSpy)  
PROP_PAGE(CLSID_StockFontPage)  
END_PROPERTY_MAP()  
```  
  
 Entsprechend wird der Code in ccomspy.h geändert und COM\-Typen nach Bedarf hinzugefügt.  
  
```  
BEGIN_PROPERTY_MAP(CComSpy)  
PROP_ENTRY_TYPE_EX( "LogFile", DISPID_LOGFILE, CLSID_ComSpyPropPage, IID_IComSpy, VT_BSTR)  
PROP_ENTRY_TYPE_EX( "ShowGridLines", DISPID_GRIDLINES, CLSID_ComSpyPropPage, IID_IComSpy, VT_BOOL)  
PROP_ENTRY_TYPE_EX( "Audit", DISPID_AUDIT, CLSID_ComSpyPropPage, IID_IComSpy, VT_BOOL)  
PROP_ENTRY_TYPE_EX( "ColWidth", DISPID_COLWIDTH, CLSID_ComSpyPropPage, IID_IComSpy, VT_UINT)  
PROP_PAGE(CLSID_StockFontPage)  
END_PROPERTY_MAP()  
```  
  
 Wir kommen nun zu den letzten Warnmeldungen, die ebenfalls durch strengere Überprüfungen der Compilerkonformität ausgelöst werden.  
  
  **\\spy\\comspyctl\\usersub.h\(70\): Warnung C4457: Durch die Deklaration von „var“ wird der Funktionsparameter ausgeblendet**  
**\\spy\\comspyctl\\usersub.h\(48\): Hinweis: Siehe Deklaration von „var“**  
**\\spy\\comspyctl\\usersub.h\(94\): Warnung C4018: „\<“: Konflikt zwischen „signed“ und „unsigned“**  
 **ComSpy.cpp**  
**\\spy\\comspyctl\\comspy.cpp\(186\): Warnung C4457: Durch die Deklaration von „bHandled“ wird der Funktionsparameter ausgeblendet**  
**\\spy\\spy\\comspyctl\\comspy.cpp\(177\): Hinweis: Siehe Deklaration von „bHandled“** Warnung C4018 stammt aus dem folgenden Code:  
  
```  
for (i=0;i<lCount;i++)  
    CoTaskMemFree(pKeys[i]);  
```  
  
 Das Problem besteht darin, dass i als UINT und lCount als „long“ deklariert ist, wodurch es zu dem Konflikt zwischen „signed“ und „unsigned“ kommt.  Es wäre unpraktisch, den Typ von lCount in UINT zu ändern, da dieser seinen Wert aus IMtsEventInfo::get\_Count erhält, der den Typ „long“ verwendet und sich nicht im Benutzercode befindet.  Daher wird eine Umwandlung zu dem Code hinzugefügt.  Eine Umwandlung im C\-Stil kann für eine numerische Konvertierung wie diese verwendet werden, das empfohlene Format ist jedoch static\_cast.  
  
```  
for (i=0;i<static_cast<UINT>(lCount);i++)  
    CoTaskMemFree(pKeys[i]);  
```  
  
 Diese Warnungen betreffen Fälle, in denen eine Variable in einer Funktion deklariert wurde, die einen Parameter mit dem gleichen Namen aufweist, was zu möglicherweise irreführendem Code führt.  Dies wurde durch Änderung der Namen der lokalen Variablen behoben.  
  
```  
  
```  
  
### Schritt 3Testen und Debuggen  
 Die App wurde getestet, indem zuerst die verschiedenen Menüs und Befehle ausgeführt wurden und dann die Anwendung geschlossen wurde.  Das einzige Problem war eine Debugassertion beim Schließen der Anwendung.  Das Problem wurde im Destruktor für CWindowImpl angezeigt. Dies ist eine Basisklasse des CSpyCon\-Objekts, der wichtigsten COM\-Komponente der Anwendung.  Der Assertionsfehler ist im folgenden Code in atlwin.h aufgetreten.  
  
```  
virtual ~CWindowImplRoot()  
{  
#ifdef _DEBUG  
if(m_hWnd != NULL)// should be cleared in WindowProc  
{  
ATLTRACE(atlTraceWindowing, 0, _T("ERROR - Object deleted before window was destroyed\n"));  
ATLASSERT(FALSE);  
}  
#endif //_DEBUG  
}  
```  
  
 Normalerweise wird hWnd in der WindowProc\-Funktion auf NULL festgelegt. Dies passierte jedoch nicht, da statt des standardmäßigen WindowProc ein benutzerdefinierter Handler für die Windows\-Meldung \(WM\_SYSCOMMAND\) aufgerufen wurde, der das Fenster schließt.  Der benutzerdefinierte Handler hat hWnd nicht auf NULL festgelegt.  Ein Blick auf ähnlichen Code in der CWnd\-Klasse von MFC zeigt, dass beim Zerstören eines Fensters OnNcDestroy aufgerufen wird. Gemäß den Empfehlungen in der Dokumentation zu MFC sollte beim Überschreiben von CWnd::OnNcDestroy das einfache NcDestroy aufgerufen werden, um sicherzustellen, dass die richtigen Bereinigungen durchgeführt werden. Dazu gehört auch das Trennen des Fensterhandles vom Fenster, oder – anders ausgedrückt – das Festlegen von hWnd auf NULL.  Diese Bestätigung kann auch in der ursprünglichen Version des Beispiels ausgelöst worden sein, da der gleiche Assertionscode auch in der alten Version von atlwin.h vorhanden war.  
  
 Um die Funktionalität der App zu testen, wurde mithilfe der ATL\-Projektvorlage eine Serviced Component erstellt und im ATL\-Projektassistenten COM\+\-Unterstützung hinzugefügt.  Wenn Sie zuvor nicht mit Serviced Components gearbeitet haben, können Sie problemlos eine solche erstellen, registrieren und zur Verwendung durch andere Apps im System oder Netzwerk verfügbar machen.  Mit der COM Spy\-App kann die Aktivität von Serviced Components zu Diagnosezwecken überwacht werden.  
  
 Dann wurde eine Klasse hinzugefügt, ATL Object ausgewählt und der Objektname als „Dog“ angegeben.  In dog.h und dog.cpp wurde dann die Implementierung hinzugefügt.  
  
```  
STDMETHODIMP CDog::Wag(LONG* lDuration)  
{  
    // TODO: Add your implementation code here  
    *lDuration = 100l;  
    return S_OK;  
}  
```  
  
 Als Nächstes wurde es erstellt und registriert \(dazu müssen Sie Visual Studio als Administrator ausführen\) und mithilfe der Serviced Component\-Anwendung in der Windows\-Systemsteuerung aktiviert.  Es wurde ein C\#\-Windows Forms\-Projekt erstellt, eine Schaltfläche aus der Toolbox in das Formular gezogen und durch Doppelklick ein Click\-Ereignishandler erstellt.  Zum Instanziieren der Dog\-Komponente wurde folgender Code hinzugefügt.  
  
```  
private void button1_Click(object sender, EventArgs e)  
{  
    ATLProjectLib.Dog dog1 = new ATLProjectLib.Dog();  
    dog1.Wag();  
}  
```  
  
 Dies erfolgte ohne Probleme. Nach dem Ausführen und der Konfigurierung von COM Spy zur Überwachung der Dog\-Komponente werden zahlreiche Daten über die Aktivität angezeigt.  
  
## Siehe auch  
 [Portieren und Aktualisieren: Beispiele und Fallstudien](../porting/porting-and-upgrading-examples-and-case-studies.md)   
 [Nächstes Beispiel: Spy\+\+](../porting/porting-guide-spy-increment.md)   
 [Vorheriges Beispiel: MFC Scribble](../porting/porting-guide-mfc-scribble.md)