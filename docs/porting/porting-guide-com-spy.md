---
title: 'Leitfaden zum Portieren: COM Spy | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 24aa0d52-4014-4acb-8052-f4e2e4bbc3bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f284d41532d9b57f794d056863536b057bb6b3dd
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33845608"
---
# <a name="porting-guide-com-spy"></a>Leitfaden zum Portieren: COM Spy
Dieses Thema ist das zweite aus einer Reihe von Artikeln, die die Aktualisierung älterer Visual C++-Projekte auf die neueste Version von Visual Studio veranschaulichen. Der Beispielcode in diesem Thema wurde zuletzt mit Visual Studio 2005 kompiliert.  
  
## <a name="comspy"></a>COMSpy  
 COMSpy ist ein Programm, das die Aktivität von Serviced Components auf einem Computer überwacht und protokolliert. Serviced Components sind COM+-Komponenten, die auf einem System ausgeführt werden und von Computern im selben Netzwerk verwendet werden können. Sie werden durch die Funktion „Komponentendienste“ in der Windows-Systemsteuerung verwaltet.  
  
### <a name="step-1-converting-the-project-file"></a>Schritt 1. Konvertieren der Projektdatei  
 Die Projektdatei lässt sich problemlos konvertieren und erstellt einen Migrationsbericht. Einige Einträge in dem Bericht geben Hinweise auf Probleme, die eventuell beseitigt werden müssen. Im Folgenden eines der gemeldeten Probleme. Beachten Sie, dass Fehlermeldungen in diesem Thema zur besseren Lesbarkeit manchmal gekürzt werden; z. B. werden die vollständigen Pfade teilweise entfernt.  
  
```Output  
ComSpyAudit\ComSpyAudit.vcproj: MSB8012: $(TargetPath) ('C:\Users\UserName\Desktop\spy\spy\ComSpyAudit\.\XP32_DEBUG\ComSpyAudit.dll') does not match the Librarian's OutputFile property value '.\XP32_DEBUG\ComSpyAudit.dll' ('C:\Users\UserName\Desktop\spy\spy\XP32_DEBUG\ComSpyAudit.dll') in project configuration 'Unicode Debug|Win32'. This may cause your project to build incorrectly. To correct this, please make sure that $(TargetPath) property value matches the value specified in %(Lib.OutputFile).  
```  
  
 Ein häufiges Problem beim Upgrade von Projekten besteht darin, dass die Linker-OutputFile-Einstellung im Dialogfeld „Projekteigenschaften“ eventuell überprüft werden muss. Bei Projekten vor Visual Studio 2010 ist OutputFile eine Einstellung, die dem Assistenten für die automatische Konvertierung Probleme bereitet, wenn sie nicht auf einen Standardwert festgelegt ist. In diesem Fall wurden die Pfade für die Ausgabedateien auf den nicht standardmäßigen Ordner XP32_DEBUG festgelegt. Weitere Informationen zu diesem Fehler haben wir in einem [Blogbeitrag](http://blogs.msdn.com/b/vcblog/archive/2010/03/02/visual-studio-2010-c-project-upgrade-guide.aspx) zum Visual C++ 2010-Projektupgrade gefunden, einem Upgrade, bei dem der wichtige Wechsel von vcbuild zu msbuild erfolgte. Gemäß den Informationen in diesem Blogbeitrag lautet der Standardwert für die OutputFile-Einstellung beim Erstellen eines neuen Projekts $(OutDir)$(TargetName)$(TargetExt), doch wird dieser Wert nicht bei der Konvertierung festgelegt, da die Überprüfung der Richtigkeit für konvertierte Projekte nicht möglich ist.  Wir prüfen nun trotzdem, ob dies für OutputFile möglich ist.  Es funktioniert und wir können den Vorgang fortsetzen. Wenn es keinen bestimmten Grund für die Verwendung eines nicht dem Standard entsprechenden Ausgabeordners gibt, wird die Verwendung des standardmäßigen Speicherorts empfohlen. In diesem Fall haben wir als Ausgabespeicherort während der Portierung und Aktualisierung den nicht standardmäßigen Speicherort belassen. $(OutDir) wird in der Debugkonfiguration in den XP32_DEBUG-Ordner und in der Releasekonfiguration in den ReleaseU-Ordner aufgelöst.  
  
### <a name="step-2-getting-it-to-build"></a>Schritt 2 Erstellen des Projekts  
 Beim Erstellen des portierten Projekts treten eine Reihe von Fehlern und Warnungen auf.  
  
 ComSpyCtl wird aufgrund des folgenden Fehlers nicht kompiliert:  
  
```Output  
atlcom.h(611): error C2664: 'HRESULT CComSpy::IPersistStreamInit_Save(LPSTREAM,BOOL,ATL::ATL_PROPMAP_ENTRY *)': cannot convert argument 3 from 'const ATL::ATL_PROPMAP_ENTRY *' to 'ATL::ATL_PROPMAP_ENTRY *'atlcom.h(611): note: Conversion loses qualifiersatlcom.h(608): note: while compiling class template member function 'HRESULT ATL::IPersistStreamInitImpl<CComSpy>::Save(LPSTREAM,BOOL)'\spy\spy\comspyctl\ccomspy.h(28): note: see reference to class template instantiation 'ATL::IPersistStreamInitImpl<CComSpy>' being compiled  
```  
  
 Die Fehlermeldung verweist auf die Save-Methode für die Klasse IPersistStreamInitImpl in atlcom.h.  
  
```cpp  
STDMETHOD(Save)(_Inout_ LPSTREAM pStm, _In_ BOOL fClearDirty)  
{  
     T* pT = static_cast<T*>(this);  
     ATLTRACE(atlTraceCOM, 2, _T("IPersistStreamInitImpl::Save\n"));  
     return pT->IPersistStreamInit_Save(pStm, fClearDirty, T::GetPropertyMap());  
}  
```  
  
 Das Problem besteht darin, dass eine Konvertierung, die von einer älteren Version des Compilers akzeptiert wurde, nicht mehr gültig ist. Um dem C++-Standard zu entsprechen, wird zuvor zulässiger Code nicht mehr zugelassen. In diesem Fall ist es nicht sicher, einen nicht konstanten Zeiger an eine Funktion zu übergeben, die einen konstanten Zeiger erwartet.  Die Lösung besteht darin, die Deklaration von IPersistStreamInit_Save in der CComSpy-Klasse zu suchen und den const-Modifizierer zu dem dritten Parameter hinzuzufügen.  
  
```cpp  
HRESULT CComSpy::IPersistStreamInit_Save(LPSTREAM pStm, BOOL /* fClearDirty */, const ATL_PROPMAP_ENTRY* pMap)  
  
```  
  
 Eine ähnliche Änderung wird an IPersistStreamInit_Load vorgenommen.  
  
```cpp  
HRESULT IPersistStreamInit_Load(LPSTREAM pStm, const ATL_PROPMAP_ENTRY* pMap);  
```  
  
 Der nächste Fehler befasst sich mit der Registrierung.  
  
```Output  
error MSB3073: The command "regsvr32 /s /c "C:\Users\username\Desktop\spy\spy\ComSpyCtl\.\XP32_DEBUG\ComSpyCtl.lib"error MSB3073: echo regsvr32 exec. time > ".\XP32_DEBUG\regsvr32.trg"error MSB3073:error MSB3073: :VCEnd" exited with code 3.  
```  
  
 Dieser Postbuild-Registrierungsbefehl wird nicht mehr benötigt. Stattdessen wird einfach der benutzerdefinierte Befehl entfernt und in den Linker-Einstellungen angegeben, um die Ausgabe zu registrieren.  
  
### <a name="dealing-with-warnings"></a>Umgang mit Warnungen  
 Das Projekt erzeugt die folgende Linkerwarnung.  
  
```Output  
warning LNK4075: ignoring '/EDITANDCONTINUE' due to '/SAFESEH' specification  
```  
  
 Die Compileroption /SAFESEH ist im Debugmodus nicht geeignet. Hier ist /EDITANDCONTINUE nützlich; die Lösung besteht also darin, /SAFESEH ausschließlich für Debugkonfigurationen zu deaktivieren. Dazu wird das Eigenschaftendialogfeld des Projekts geöffnet, das den Fehler produziert, und zuerst die Konfiguration auf Debuggen (Debug Unicode) festgelegt. Danach wird im Abschnitt „Erweitert“ die Eigenschaft „Image weist sichere Ausnahmehandler auf“ auf „Nein“ zurückgesetzt (/SAFESEH:NO).  
  
 Der Compiler warnt uns davor, dass PROP_ENTRY_EX veraltet ist. Es ist nicht sicher und der empfohlene Ersatz ist PROP_ENTRY_TYPE_EX.  
  
```cpp  
BEGIN_PROPERTY_MAP(CComSpy)  
     PROP_ENTRY_EX( "LogFile", DISPID_LOGFILE, CLSID_ComSpyPropPage, IID_IComSpy)  
     PROP_ENTRY_EX( "ShowGridLines", DISPID_GRIDLINES, CLSID_ComSpyPropPage, IID_IComSpy)  
     PROP_ENTRY_EX( "Audit", DISPID_AUDIT, CLSID_ComSpyPropPage, IID_IComSpy)  
     PROP_ENTRY_EX( "ColWidth", DISPID_COLWIDTH, CLSID_ComSpyPropPage, IID_IComSpy)  
     PROP_PAGE(CLSID_StockFontPage)  
END_PROPERTY_MAP()  
```  
  
 Entsprechend wird der Code in ccomspy.h geändert und COM-Typen nach Bedarf hinzugefügt.  
  
```cpp  
BEGIN_PROPERTY_MAP(CComSpy)  
     PROP_ENTRY_TYPE_EX( "LogFile", DISPID_LOGFILE, CLSID_ComSpyPropPage, IID_IComSpy, VT_BSTR)  
     PROP_ENTRY_TYPE_EX( "ShowGridLines", DISPID_GRIDLINES, CLSID_ComSpyPropPage, IID_IComSpy, VT_BOOL)  
     PROP_ENTRY_TYPE_EX( "Audit", DISPID_AUDIT, CLSID_ComSpyPropPage, IID_IComSpy, VT_BOOL)  
     PROP_ENTRY_TYPE_EX( "ColWidth", DISPID_COLWIDTH, CLSID_ComSpyPropPage, IID_IComSpy, VT_UINT)  
     PROP_PAGE(CLSID_StockFontPage)  
END_PROPERTY_MAP()  
```  
  
 Wir kommen nun zu den letzten Warnmeldungen, die ebenfalls durch strengere Überprüfungen der Compilerkonformität ausgelöst werden.  
  
```Output  
\spy\comspyctl\usersub.h(70): warning C4457: declaration of 'var' hides function parameter\spy\comspyctl\usersub.h(48): note: see declaration of 'var'\spy\comspyctl\usersub.h(94): warning C4018: '<': signed/unsigned mismatch  ComSpy.cpp\spy\comspyctl\comspy.cpp(186): warning C4457: declaration of 'bHandled' hides function parameter\spy\spy\comspyctl\comspy.cpp(177): note: see declaration of 'bHandled'  
```  
  
 Warnung C4018 stammt aus dem folgenden Code:  
  
```cpp  
for (i=0;i<lCount;i++)  
    CoTaskMemFree(pKeys[i]);  
```  
  
 Das Problem besteht darin, dass i als UINT und lCount als „long“ deklariert ist, wodurch es zu dem Konflikt zwischen „signed“ und „unsigned“ kommt. Es wäre unpraktisch, den Typ von lCount in UINT zu ändern, da dieser seinen Wert aus IMtsEventInfo::get_Count erhält, der den Typ „long“ verwendet und sich nicht im Benutzercode befindet. Daher wird eine Umwandlung zu dem Code hinzugefügt. Eine Umwandlung im C-Stil kann für eine numerische Konvertierung wie diese verwendet werden, das empfohlene Format ist jedoch static_cast.  
  
```cpp  
for (i=0;i<static_cast<UINT>(lCount);i++)  
    CoTaskMemFree(pKeys[i]);  
```  
  
 Diese Warnungen betreffen Fälle, in denen eine Variable in einer Funktion deklariert wurde, die einen Parameter mit dem gleichen Namen aufweist, was zu möglicherweise irreführendem Code führt. Dies wurde durch Änderung der Namen der lokalen Variablen behoben.  
  
### <a name="step-3-testing-and-debugging"></a>Schritt 3 Testen und Debuggen  
 Die App wurde getestet, indem zuerst die verschiedenen Menüs und Befehle ausgeführt wurden und dann die Anwendung geschlossen wurde. Das einzige Problem war eine Debugassertion beim Schließen der Anwendung. Das Problem wurde im Destruktor für CWindowImpl angezeigt. Dies ist eine Basisklasse des CSpyCon-Objekts, der wichtigsten COM-Komponente der Anwendung. Der Assertionsfehler ist im folgenden Code in atlwin.h aufgetreten.  
  
```cpp  
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
  
 Normalerweise wird hWnd in der WindowProc-Funktion auf NULL festgelegt. Dies passierte jedoch nicht, da statt des standardmäßigen WindowProc ein benutzerdefinierter Handler für die Windows-Meldung (WM_SYSCOMMAND) aufgerufen wurde, der das Fenster schließt. Der benutzerdefinierte Handler hat hWnd nicht auf NULL festgelegt. Ein Blick auf ähnlichen Code in der CWnd-Klasse von MFC zeigt, dass beim Zerstören eines Fensters OnNcDestroy aufgerufen wird. Gemäß den Empfehlungen in der Dokumentation zu MFC sollte beim Überschreiben von CWnd::OnNcDestroy das einfache NcDestroy aufgerufen werden, um sicherzustellen, dass die richtigen Bereinigungen durchgeführt werden. Dazu gehört auch das Trennen des Fensterhandles vom Fenster, oder – anders ausgedrückt – das Festlegen von hWnd auf NULL. Diese Bestätigung kann auch in der ursprünglichen Version des Beispiels ausgelöst worden sein, da der gleiche Assertionscode auch in der alten Version von atlwin.h vorhanden war.  
  
 Um die Funktionalität der App zu testen, wurde mithilfe der ATL-Projektvorlage eine Serviced Component erstellt und im ATL-Projektassistenten COM+-Unterstützung hinzugefügt. Wenn Sie zuvor nicht mit Serviced Components gearbeitet haben, können Sie problemlos eine solche erstellen, registrieren und zur Verwendung durch andere Apps im System oder Netzwerk verfügbar machen. Mit der COM Spy-App kann die Aktivität von Serviced Components zu Diagnosezwecken überwacht werden.  
  
 Dann wurde eine Klasse hinzugefügt, ATL Object ausgewählt und der Objektname als „Dog“ angegeben. In dog.h und dog.cpp wurde dann die Implementierung hinzugefügt.  
  
```cpp  
STDMETHODIMP CDog::Wag(LONG* lDuration)  
{  
    // TODO: Add your implementation code here  
    *lDuration = 100l;  
    return S_OK;  
}  
```  
  
 Als Nächstes wurde es erstellt und registriert (dazu müssen Sie Visual Studio als Administrator ausführen) und mithilfe der Serviced Component-Anwendung in der Windows-Systemsteuerung aktiviert. Es wurde ein C#-Windows Forms-Projekt erstellt, eine Schaltfläche aus der Toolbox in das Formular gezogen und durch Doppelklick ein Click-Ereignishandler erstellt. Zum Instanziieren der Dog-Komponente wurde folgender Code hinzugefügt.  
  
```cpp  
private void button1_Click(object sender, EventArgs e)  
{  
    ATLProjectLib.Dog dog1 = new ATLProjectLib.Dog();  
    dog1.Wag();  
}  
```  
  
 Dies erfolgte ohne Probleme. Nach dem Ausführen und der Konfigurierung von COM Spy zur Überwachung der Dog-Komponente werden zahlreiche Daten über die Aktivität angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Portieren und Aktualisieren: Beispiele und Fallstudien](../porting/porting-and-upgrading-examples-and-case-studies.md)   
 [Nächstes Beispiel: Spy++](../porting/porting-guide-spy-increment.md)   
 [Vorheriges Beispiel: MFC Scribble](../porting/porting-guide-mfc-scribble.md)