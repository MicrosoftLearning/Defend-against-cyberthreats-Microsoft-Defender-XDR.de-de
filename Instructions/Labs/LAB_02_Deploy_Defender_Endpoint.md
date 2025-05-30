---
lab:
  title: Bereitstellen von Microsoft Defender für Endpunkt
  module: Mitigate threats using Microsoft Defender for Endpoint'
---

# Bereitstellen von Microsoft Defender für Endpunkt

## Labszenario

Sie arbeiten als Security Operations Analyst in einem Unternehmen, das Microsoft Defender für Endpunkt implementiert. Ihr Vorgesetzter plant, einige Geräte zu integrieren, um einen Einblick in die erforderlichen Änderungen der Reaktionsverfahren des SecOps-Teams zu erhalten.

Zunächst initialisieren Sie die Defender for Endpoint-Umgebung. Danach führen Sie das Onboarding der ersten Geräte für die Bereitstellung durch, indem Sie das Onboardingskript auf den Geräten ausführen. Sie konfigurieren die Sicherheit für die Umgebung. Schließlich erstellen Sie Gerätegruppen und weisen die entsprechenden Geräte zu.

>**Wichtig:** Die virtuellen Lab-Computer werden über verschiedene Module verwendet. SPEICHERN Sie Ihre virtuellen Computer. Wenn Sie das Lab verlassen, ohne zu speichern, müssen Sie einige Konfigurationen erneut durchführen.

>**Hinweis:** Vergewissern Sie sich, dass Sie Aufgabe 1 des vorherigen Moduls erfolgreich abgeschlossen haben.

Diese Übung dauert ca. **15** Minuten.

### Aufgabe 1: Initialisieren von Microsoft Defender for Endpunkt

In dieser Aufgabe führen Sie die Initialisierung von Microsoft Defender for Endpoint durch.

1. Melden Sie sich als Admin bei der virtuellen Maschine **WIN1** mit dem Passwort: **Pa55w.rd** an.  

1. Wenn Sie sich noch nicht im Microsoft Defender XDR-Portal befinden, starten Sie den Microsoft Edge-Browser.

1. Wechseln Sie im Edge-Browser zum Microsoft Defender XDR-Portal unter (<https://security.microsoft.com>).

1. Kopieren Sie im Dialogfeld **Anmelden**das von Ihrem Labhostinganbieter bereitgestellte Mandanten-E-Mail-Konto für den Administrator, und fügen Sie es ein, und wählen Sie dann **Weiter** aus.

1. Kopieren Sie im Dialogfeld **Kennwort eingeben** das von Ihrem Labhostinganbieter bereitgestellte Mandantenkennwort für den Administrator, und fügen Sie es ein, und wählen Sie dann **Anmelden** aus.

    >**Tipp:** Das Administrator-E-Mail-Konto und Kennwort des Mandanten finden Sie auf der Registerkarte „Ressourcen“.

1. Scrollen Sie auf dem **Defender XDR**-Portal im Navigationsmenü auf der linken Seite nach unten, erweitern Sie den Abschnitt **System** und wählen Sie **Einstellungen** aus.

1. Wählen Sie auf der Seite „Einstellungen“ die Option **Geräteermittlung** aus.

    >**Hinweis:** Wenn Sie die Option **Geräteerkennung** unter **Einstellungen** nicht sehen, melden Sie sich ab, indem Sie auf den Kreis mit Ihren Kontoinitialen oben rechts klicken und dann auf **Abmelden**. Sie können auch versuchen, die Seite mit STRG+F5 zu aktualisieren oder InPrivate zu öffnen. Melden Sie sich erneut mit den **E-Mail des Mandanten**-Anmeldeinformationen an.

1. Stellen Sie im Setup der Ermittlung sicher, dass **Standardermittlung (empfohlen)** ausgewählt ist. 

    >**Tipp:** Wenn Sie die Option nicht sehen, aktualisieren Sie die Seite.


### Aufgabe 2: Ein Gerät einbinden

In dieser Aufgabe integrieren Sie ein Gerät in Microsoft Defender for Endpoint mithilfe eines Onboardingskripts.

1. Scrollen Sie im **Defender XDR**-Portal im Navigationsmenü auf der linken Seite nach unten und erweitern Sie den Abschnitt **System**, wählen Sie **Einstellungen** und wählen Sie dann auf der Seite Einstellungen **Endpunkte** aus.

1. Wählen Sie **Onboarding** im Abschnitt Geräteverwaltung aus.

    >**Hinweis:** Sie können das Onboarding von Geräten auch über den Abschnitt **Objekte** in der linken Menüleiste durchführen. Erweitern Sie Objekte, und wählen Sie Geräte aus. Scrollen Sie auf der Seite Geräteinventarisierung mit der Auswahl Computer und Mobilgeräte nach unten zu **Onboarding von Geräten.** Daraufhin erscheint die Seite **Einstellungen > Endpunkte**.

1. Im Bereich „1. Gerät einbinden“ stellen Sie sicher, dass „Lokales Skript (für bis zu 10 Geräte)“ in der Dropdownliste „Bereitstellungsmethode“ angezeigt wird und klicken Sie auf die Schaltfläche **Onboarding-Paket herunterladen**.

1. Markieren Sie im Popupfenster *Downloads* die Datei „WindowsDefenderATPOnboardingPackage.zip“ mit der Maus und klicken Sie auf das Ordnersymbol **Im Ordner anzeigen**. **Tipp:** Wenn Sie es nicht sehen, sollte sich die Datei im Verzeichnis c:\users\admin\downloads befinden.

    >**Tipp:** Wenn Ihr Browser den Download blockiert, ergreifen Sie Maßnahmen im Browser, um ihn zuzulassen. Im Microsoft Edge-Browser erhalten Sie möglicherweise die Meldung „*WindowsDefenderATPOnboardingPackage.zip wird in der Regel nicht heruntergeladen. Stellen Sie sicher, dass Sie …* vertrauen, klicken Sie ggf. auf die Schaltfläche Auslassungspunkte (...) und dann auf **Beibehalten**“. In Microsoft Edge erscheint ein zweites Popupfenster mit der Meldung „*Stellen Sie sicher, dass Sie WindowsDefenderATPOnboardingPackage.zip vertrauen, bevor Sie es öffnen*“, klicken Sie auf **Mehr anzeigen**, um die Auswahl zu erweitern, und anschließend auf **Trotzdem beibehalten**.

1. Klicken Sie mit der rechten Maustaste auf die heruntergeladene Zip-Datei und wählen Sie **Alles extrahieren …**, stellen Sie sicher, dass *Extrahierte Dateien nach Abschluss anzeigen* markiert ist und klicken Sie auf **Extrahieren**.

1. Klicken Sie mit der rechten Maustaste auf die extrahierte Datei „WindowsDefenderATPLocalOnboardingScript.cmd“ und wählen Sie **Eigenschaften** aus. Markieren Sie das Kontrollkästchen **Entsperren** unten rechts im Eigenschaftenfenster und klicken Sie auf **OK**.

1. Klicken Sie erneut mit der rechten Maustaste auf die extrahierte Datei „WindowsDefenderATPLocalOnboardingScript.cmd“ und wählen Sie **Als Administrator ausführen** aus.  **Tipp:** Wenn das Windows SmartScreen-Fenster erscheint, klicken Sie auf **Mehr Info** und wählen Sie **trotzdem ausführen** aus.

1. Wenn das Fenster „Benutzerkontensteuerung“ angezeigt wird, wählen Sie **Ja** aus, damit das Skript ausgeführt werden kann, beantworten Sie die vom Skript gestellte Frage mit **Ja** und drücken Sie die **Eingabetaste**. Wenn Sie fertig sind, sollten Sie eine Meldung auf dem Befehlsbildschirm sehen, die besagt: *Computer erfolgreich in Microsoft Defender for Endpoint integriert*.

1. Press any key to continue... Damit wird das Eingabeaufforderungsfenster geschlossen.

### Aufgabe 3: Konfigurieren von Rollen

In dieser Aufgabe konfigurieren Sie Rollen für die Verwendung mit Gerätegruppen.

1. Erweitern Sie im Navigationsmenü des Microsoft Defender XDR-Portals den Abschnitt **System** und wählen Sie **Einstellungen**, dann **Microsoft Defender XDR** aus.

1. Wählen Sie **Berechtigungen und Rollen** unter dem Abschnitt *Konto* aus.

1. Scrollen Sie auf der Seite nach unten und wählen Sie den Link **Zu Berechtigungen und Rollen wechseln**.

1. Auf der Seite *Berechtigungen und Rollen* wählen Sie **+ Benutzerdefinierte Rolle erstellen**.

1. Auf der Seite *Grundlagen* im Dialogfeld „Rolle hinzufügen“ geben Sie Folgendes ein:

    |Grundlegende Einstellungen|Wert|
    |---|---|
    |Rollenname|**Support der Ebene 1**|

1. Wählen Sie **Weiter** aus.

1. Auf der Seite **Berechtigungen** wählen Sie die folgenden Berechtigungen aus:

    |Berechtigungsgruppe|Beschreibung|  |Sicherheitsvorgänge|Verwaltet alltägliche Vorgänge und reagiert auf Vorfälle und Empfehlungen|

1. Wählen Sie auf der Popout-Seite für *Sicherheitsvorgänge* das Optionsfeld **Alle Lese- und Verwaltungsrechte**.

1. Wählen Sie **Anwenden** und anschließend **Weiter**.

1. Wählen Sie auf der Seite **Benutzer und Datenquellen zuweisen** die Schaltfläche **Zuweisung erstellen**.

1. Im Dialog *Zuweisung hinzufügen* geben Sie Folgendes ein:

    |Zuweisungseinstellungen|Wert|
    |---|---|
    |Zuweisungsname|**Support der Ebene 1**|
    |Employees|****sg-IT**|
    |Datenquellen|**Standardeinstellung beibehalten**|

1. Wählen Sie **Hinzufügen** aus und dann **Weiter**.

1. Klicken Sie auf **Senden** und dann auf **Fertig**, wenn Sie fertig sind.

### Aufgabe 4: Konfigurieren von Gerätegruppen

In dieser Aufgabe konfigurieren Sie Gerätegruppen, die die Zugriffssteuerung und die Automatisierungskonfiguration ermöglichen.

1. Erweitern Sie in der linken Menüleiste des Microsoft Defender XDR-Portals den Abschnitt **System** und wählen Sie **Einstellungen**, dann **Endpunkte** aus.

1. Wählen Sie im Bereich Berechtigungen die Option **Gerätegruppen** aus.

1. Wählen Sie das Symbol **+ Gerätegruppe hinzufügen** aus.

1. Geben Sie auf der Registerkarte Allgemein die folgenden Informationen ein:

    |Allgemeine Einstellung|Wert|
    |---|---|
    |Name der Gerätegruppe|**Regulär**|
    |Wartungsebene|Vollständig – Wartung|

1. Wählen Sie **Weiter** aus.

1. Wählen Sie auf der Registerkarte „Geräte“ für die Betriebssystembedingung **Windows 11** aus und klicken Sie auf **Weiter**.

    >**Hinweis:** Einige Lab-Hosting-Anbieter haben möglicherweise noch *Windows 10* Images für WIN1. Sie können eines oder beide auswählen.

1. Auf der Registerkarte „Gerätevorschau“ könnte die Schaltfläche *Vorschau anzeigen* den virtuellen Computer WIN1 anzeigen, aber höchstwahrscheinlich sind die Daten noch nicht ausgefüllt. Klicken Sie auf **Weiter**, um fortzufahren.

1. Wählen Sie auf der Registerkarte Benutzerzugriff die Option **sg-IT** und dann die Schaltfläche **Ausgewählte Gruppen hinzufügen** aus. Vergewissern Sie sich, dass die Gruppe unter *Azure AD-Benutzergruppen mit Zugriff auf diese Gerätegruppe* angezeigt wird.

1. Klicken Sie auf **Senden** und dann auf **Fertig**, wenn Sie fertig sind.

1. Wählen Sie in der Informationsnachricht *Gerätegruppenkonfiguration wurde die Konfiguration geändert. Änderungen anwenden, um Übereinstimmungen zu überprüfen und Gruppierungen neu zu berechnen* **Änderungen anwenden** aus.

1. Sie haben jetzt zwei Gerätegruppen: die von Ihnen erstellte Gruppe „Regulär“ und die Gruppe „Nicht gruppierte Geräte (Standard)“ mit der gleichen Korrekturstufe.

## Fahren Sie mit Übung 2 fort
