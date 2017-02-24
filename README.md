# Mental_Health_Services_Haringey
Mental Health Services in Haringey
<!DOCTYPE html>
<html>
<head>
	<title>Mental Health Services in Haringey - A-Team</title>
	<meta charset="utf-8" />



	<link rel="stylesheet" href="stylesheets/leaflet.css" />

     <script src="javascripts/leaflet.js"></script>
</head>



<body>
	<div id="map" style="height: 650px"></div>

<script>      

var LeafIcon = L.Icon.extend({
			options: {
				iconSize:     [23, 43],
				iconAnchor:   [11, 46],
				popupAnchor:  [1, -66]
			}
		});

var boundary = new L.layerGroup();

   L.polygon([
	[51.609438215600136,-0.127902246381305],
	[51.609301727865464,-0.126336519589241], 
	[51.610018041101391,-0.125355250500741], 
	[51.609944187123425,-0.124897571301291], 
	[51.608706774302199,-0.123543324143282], 
	[51.608363942053117,-0.119203139276032], 
	[51.60865231064539,-0.118736288769389], 
	[51.60820023259987,-0.117517285667444], 
	[51.608434877924765,-0.117289501486984], 
	[51.608612451420356,-0.110823564291747], 
	[51.608339856175505,-0.110424722239761], 
	[51.608427148786483,-0.10351481785545], 
	[51.608043582466472,-0.102538628745315], 
	[51.608489985906047,-0.101783459466395], 
	[51.60846364038521,-0.099099741330744], 
	[51.60852111809632,-0.097485581063302], 
	[51.608923549996838,-0.097681059563254], 
	[51.609297910081004,-0.095812432051321], 
	[51.608656915638001,-0.095157576258738], 
	[51.609000900820625,-0.093580504328668], 
	[51.608846441779235,-0.092486464337853], 
	[51.609097089443139,-0.09247162478446], 
	[51.608790815087268,-0.091443167419472], 
	[51.608816676963194,-0.089716216402944], 
	[51.608468658290697,-0.085851626457058], 
	[51.608452549080326,-0.07562715609164], 
	[51.608791708744462,-0.070869922130559], 
	[51.608642889128809,-0.067508267598703], 
	[51.608938978827297,-0.067140408321432], 
	[51.608587026238936,-0.065045327376432], 
	[51.608863034510108,-0.054379380499716], 
	[51.608505048188427,-0.052910011100518], 
	[51.608100482107545,-0.052915767800109], 
	[51.607355402376605,-0.050231105628109], 
	[51.605634584706131,-0.041447876199425], 
	[51.602813466603742,-0.043540415434819], 
	[51.599788608839603,-0.046468827285956], 
	[51.596850593305476,-0.050298427065463], 
	[51.59495731593843,-0.051251567125791], 
	[51.594045899688652,-0.052252134577114], 
	[51.592442700623025,-0.052532944977356], 
	[51.590834060094039,-0.05340731759462], 
	[51.589606089179988,-0.053377524395734], 
	[51.587833341442391,-0.052165629423949], 
	[51.586929906322453,-0.053159902531475], 
	[51.585912774392305,-0.054727740136651], 
	[51.583994635634447,-0.05602794529841], 
	[51.582407680543938,-0.057996645085517], 
	[51.581508842424959,-0.05976124876479], 
	[51.580605391941447,-0.061357106189947], 
	[51.579586695371098,-0.062237584643148], 
	[51.57778428264232,-0.061184180251801], 
	[51.576619500299955,-0.066782943895751], 
	[51.57635707454186,-0.066737794350639], 
	[51.575690545460205,-0.070934018749196], 
	[51.575681724845381,-0.074448564162932], 
	[51.57532469326474,-0.07532378910585], 
	[51.575492312047857,-0.075784300045867], 
	[51.574931567845375,-0.07624670556308], 
	[51.575640454304398,-0.080876831268559], 
	[51.574701083833361,-0.087231661186229], 
	[51.574292359937871,-0.086872159324062], 
	[51.574386169114625,-0.089981089851706], 
	[51.574003528643573,-0.091389755908102], 
	[51.573974436989872,-0.093583094884078], 
	[51.573588984354046,-0.094710426117311], 
	[51.573814999174459,-0.096613119806407], 
	[51.573652202818593,-0.097664741454138], 
	[51.570698228697871,-0.096115593089725], 
	[51.567125179713216,-0.100700386539105], 
	[51.564771281754247,-0.104391151200697], 
	[51.56463516143306,-0.104871505418489], 
	[51.565538847636731,-0.106204650274396 ], 
	[51.568605930174854,-0.110707657010046], 
	[51.570672157493597,-0.115166078033205], 
	[51.571891785971829,-0.115405684924706], 
	[51.5721902415671,-0.116127865036919], 
	[51.572572701998148,-0.115585326459636], 
	[51.573825840445345,-0.117184433994835], 
	[51.574147906716462,-0.117585304759842], 
	[51.574384708172474,-0.119567057173802], 
	[51.574733558545134,-0.118890252276713], 
	[51.575505607650513,-0.119650680395106], 
	[51.574662492346462,-0.123775363554822], 
	[51.574097454383214,-0.124880979959835], 
	[51.574153607624162,-0.127496512591569], 
	[51.573563715982395,-0.131389743249347], 
	[51.57286595614773,-0.13342714118819], 
	[51.570600635992463,-0.13834394530272], 
	[51.569397134397697,-0.140706207729624], 
	[51.569120267654064,-0.142415880417378], 
	[51.569912799110497,-0.143855430145825], 
	[51.571573748271312,-0.150350754255611], 
	[51.572193199552167,-0.158862786701175], 
	[51.572787389732667,-0.160455031665567], 
	[51.572501406455764,-0.1643008249503], 
	[51.572970269819827,-0.167373031226188], 
	[51.572429711799224,-0.171285290056077], 
	[51.573612392592992,-0.171181543111701], 
	[51.573981590781514,-0.1694840471559], 
	[51.576399350136484,-0.169753480053378], 
	[51.577426213828005,-0.169345647486203], 
	[51.576926402329413,-0.168088487178118], 
	[51.578654102359081,-0.166838420584901], 
	[51.581299324219074,-0.167219823495958], 
	[51.581955208122238,-0.166896098828117], 
	[51.582041695657331,-0.166215675085277], 
	[51.583221361093251,-0.16574670591534], 
	[51.585272979177901,-0.161350967906813], 
	[51.584460273286041,-0.1596429706729], 
	[51.585733366198873,-0.1579661538608], 
	[51.586216464716081,-0.157922075223614], 
	[51.586197657225874,-0.157182315697613], 
	[51.586568436053973,-0.157430033741605], 
	[51.58663071095841,-0.15870503195671], 
	[51.587974960250712,-0.158640577407262], 
	[51.587977183290633,-0.160273159858916], 
	[51.591579696883926,-0.159480845130241], 
	[51.592053768912628,-0.158689306344716], 
	[51.592374839685739,-0.158864004452629], 
	[51.59226527005336,-0.159675463877847], 
	[51.597476159813134,-0.161786563503232], 
	[51.605356604633336,-0.156367676220716], 
	[51.605443250099498,-0.155987250998171], 
	[51.605096767546605,-0.156141367790357], 
	[51.604136228508729,-0.154643781047763], 
	[51.602678307429734,-0.153312285502066], 
	[51.600870524056894,-0.153463600875163], 
	[51.599230695213691,-0.153030520778325], 
	[51.59745039271867,-0.15138599066662], 
	[51.599195004701244,-0.147000702709219], 
	[51.600126597708204,-0.144495064796318], 
	[51.601110185784385,-0.144199385657771], 
	[51.603287948408706,-0.1421409036762], 
	[51.604591047196195,-0.142090599884761], 
	[51.6063462012401,-0.143103506600652], 
	[51.608846176695572,-0.1434506524551], 
	[51.610192195820304,-0.138785614410406], 
	[51.611214795735918,-0.135283227253725], 
	[51.609438215600136,-0.127902246381305]],
 	{
	    color: 'black',
	    fillColor: 'white',
	    fillOpacity: 0.0
	}).addTo(boundary);


var redIcon = new LeafIcon({iconUrl: 'https://dl.dropboxusercontent.com/u/69787788/haringeymarker1%20copy.png'});

var communityassets = new L.LayerGroup();

    L.marker([51.601439, -0.086815], {icon: redIcon}).bindPopup('<img src="https://dl.dropboxusercontent.com/u/69787788/Haven_day_centre.jpeg" width="150" height="150"></br>THE HAVEN DAY CENTRE, 20A Waltheof Gardens, Tottenham, N17 1DX</br></br>The Haven Day Centre provides specialist support to 43 older people with physical disability/sensory impairment and specialises in individually developed care packages which take account of the reduced abilities of service users in various areas.</br><a href="https://www.carehome.co.uk/day_care_centre.cfm/id/65432192035">Click here for more info</a>').addTo(communityassets),
	L.marker([51.581934, -0.088774], {icon: redIcon}).bindPopup('<img src="https://dl.dropboxusercontent.com/u/69787788/NF%20website/Chestnuts3.jpg" width="250" height="200"></br>CHESTNUTS COMMUNITY CENTRE, 280 Saint Anns Road, London N15 5BN</br></br>This centre hosts:</br></br><a target="_blank" href="https://www.facebook.com/pg/Pyramid-Health-and-Social-Care-Association-264359593768367/about/?ref=page_internal">PYRAMID HEALTH AND SOCIAL CARE ASSOCIATION (PHASCA)</a></br></br>The primary aim of PHASCA is to promote the physical, mental, psychological and social health of families and children from all communities.</br></br><a').addTo(communityassets),
	L.marker([51.583349, -0.128579], {icon: redIcon}).bindPopup('<img src="http://www.communityhealthpartnerships.co.uk/uploads/images/547-365/HornseyNeighbourhoodHealthCentre_London.jpg" width="200" height="180"></br>THE HAYNES CENTRE, Neighbourhood Health Centre, 151 Park Road Hornsey, N8 8JL</br></br>The Haynes Centre in Hornsey provide services specifically for older people with varying degrees of dementia.</a>').addTo(communityassets),
	L.marker([51.589816, -0.111493], {icon: redIcon}).bindPopup('<img src="https://dl.dropboxusercontent.com/u/69787788/clarendon_centre.jpeg" width="150" height="200"></br>CLARENDON RECOVERY COLLEGE, Clarendon Road, Hornsey, N8 0DJ</br></br>This centre hosts:</br></br><a target="_blank" href="http://www.haringey.gov.uk/social-care-and-health/mental-health/clarendon-recovery-college">CLARENDON RECOVERY COLLEGE</a></br></br><a target="_blank" href="http://www.theateamprojects.com/index.html">THE A-TEAM').addTo(communityassets),
	L.marker([51.605423, -0.069790], {icon: redIcon}).bindPopup('<img src="https://c1.staticflickr.com/5/4054/4329144310_471832a5ea_b.jpg" width="290" height="200"></br>THE GRANGE DAY CENTRE, 32-34A White Hart Lane, Tottenham, N17 8DP</br></br>The Grange Centre in Tottenham provides services specifically for older people with varying degrees of dementia.</br><a target="_blank" href="https://www.carehome.co.uk/day_care_centre.cfm/id/65432192034">Click here for more info</a>').addTo(communityassets);


var blueMarker = new LeafIcon({iconUrl: 'https://dl.dropboxusercontent.com/u/69787788/nhsmarkerfinal.png'});

var NHSservices = new L.LayerGroup();

    L.marker([51.602142, -0.112054], {icon: blueMarker}).bindPopup('<img src="https://dl.dropboxusercontent.com/u/69787788/NHS_icon.png" width="100" height="90"></br> CANNING CRESCENT HEALTH CENTRE, 276-292 High Road, Wood Green, N22 8JT</br></br>This centre hosts the following NHS services:</br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101x002">COMMUNITY SUPPORT AND RECOVERY TEAM</a></br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101x001">COMMUNITY REHABILITATION TEAM</a></br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101x003">EARLY INTERVENTION SERVICE</a></br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101y001008">FORENSIC OUTREACH SERVICE</a>').addTo(NHSservices),
    L.marker([51.579965, -0.090669], {icon: blueMarker}).bindPopup('<img src="https://dl.dropboxusercontent.com/u/69787788/NHS_icon.png" width="100" height="90"></br> SAINT ANNS HOSPITAL, MENTAL HEALTH UNIT, St Anns Road, Haringey, N15 3TH</br></br>St Anns Hospital hosts the following NHS mental health departments:</br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101x00j">HEALTH PSYCHOLOGY, Block G</a></br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101x006">SEXUAL HEALTH PSYCHOLOGY</a></br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101x009">FAIRLANDS WARD</a></br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101x008">FINSBURY WARD</a></br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101x00a">HARINGEY ASSESSMENT WARD</a></br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101x00b">HARINGEY CRISIS RESOLUTION HOME TREATMENT TEAM</a></br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101x00d">ADOLESCENT OUTREACH TEAM</a></br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101x00e">CAMHS LEARNING DISABILITY TEAM - HARINGEY</a></br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101x00h">COMPLEX CARE TEAM - HARINGEY</a></br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101y004">EATING DISORDERS SERVICE</a></br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101x00i">HALLIWICK PERSONALITY DISORDER SERVICE</a></br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101x007">MENTAL HEALTH SERVICES FOR OLDER PEOPLE</a>').addTo(NHSservices),
    L.marker([51.598781, -0.066974], {icon: blueMarker}).bindPopup('<img src="https://dl.dropboxusercontent.com/u/69787788/NHS_icon.png" width="100" height="90"></br> LETS TALK IAPT - EAST HARINGEY, Lansdowne Road Health Centre, 1a Lansdowne Road, N17 0LL</br></br>Let’s Talk improving Access to Psychological Therapies (IAPT) is a free NHS evidence-based talking therapy service for people 16 years old and over, who are worried or have low mood. They provide a range of treatment programmes including one to one therapy, counselling and group work.</br></br><a target="_blank" href="http://www.lets-talk-iapt.nhs.uk/">Click here for more info</a>').addTo(NHSservices),
    L.marker([51.581919, -0.124095], {icon: blueMarker}).bindPopup('<img src="https://dl.dropboxusercontent.com/u/69787788/NHS_icon.png" width="100" height="90"></br> LETS TALK IAPT - WEST HARINGEY, Crouch End Health Centre 45 Middle Lane, N8 8PH</br></br>Let’s Talk improving Access to Psychological Therapies (IAPT) is a free NHS evidence-based talking therapy service for people 16 years old and over, who are worried or have low mood. They provide a range of treatment programmes including one to one therapy, counselling and group work.</br></br><a target="_blank" href="http://www.lets-talk-iapt.nhs.uk/">Click here for more info</a>').addTo(NHSservices),
    L.marker([51.614380, -0.074600], {icon: blueMarker}).bindPopup('<img src="https://dl.dropboxusercontent.com/u/69787788/NHS_icon.png" width="100" height="90"></br> MENTAL HEALTH LIAISON SERVICE - NORTH MIDDLESEX UNIVERSITY HOSPITAL, Sterling Way, Edmonton, N18 1QX</br></br>They support the Accident and Emergency (A&E) department at North Middlesex Hospital. They treat patients suspected of having mental health problems.</br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101x005">Click here for more info</a>').addTo(NHSservices),
    L.marker([51.614410, -0.076154], {icon: blueMarker}).bindPopup('<img src="https://dl.dropboxusercontent.com/u/69787788/NHS_icon.png" width="100" height="90"></br> AVESBURY HOUSE, 85 Tanners End Lane, off Silver Street, Edmonton, N18 1PQ</br></br>Avesbury House, part of the North London Forensic Service, provides care and rehabilitation for patients who have been in conditions of security, progressing into the community, but continue to require 24 hour nursing care.</br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101y001001">Click here for more info</a>').addTo(NHSservices),
    L.marker([51.547022, -0.105284], {icon: blueMarker}).bindPopup('<img src="https://dl.dropboxusercontent.com/u/69787788/NHS_icon.png" width="100" height="90"></br> FORENSIC INTEGRATED COMMUNITY SERVICES (FICS), Highbury Magistrates Court, 51-53 Holloway Road, N7</br></br>They offer a range of preventative solutions as well as assessment, treatment, CPA care co-ordination and supervision to mentally disordered offenders.</br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101y001002">Click here for more info</a>').addTo(NHSservices),
    L.marker([51.666504, -0.103951], {icon: blueMarker}).bindPopup('<img src="https://dl.dropboxusercontent.com/u/69787788/NHS_icon.png" width="100" height="90"></br> CHASE FARM HOSPITAL, The Ridgeway, Enfield, EN2 8JL</br></br>CHASE FARM HOSPITAL hosts the following NHS mental health services:</br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101y001003">FORENSIC FAMILY AND FRIENDS SUPPORT GROUP</a></br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101y001004">FORENSIC LEARNING DISABILITY SERVICE</a></br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101y001005">FORENSIC LOW SECURE</a></br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101y001006">FORENSIC MEDIUM SECURE INPATIENTS SERVICES</a></br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101y001007">NATIONAL STALKING CLINIC</a></br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101w00c">BED MANAGEMENT</a></br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101w006">CONINUING CARE FOR OLDER ADULTS - Cornwall Villa, Silver Birches</a></br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101w007">OLDER ADULTS INPATIENT SERVICES</a>').addTo(NHSservices),
    L.marker([51.577953, -0.100929], {icon: blueMarker}).bindPopup('<img src="https://dl.dropboxusercontent.com/u/69787788/NHS_icon.png" width="100" height="90"></br> CAMHS TIER 3 TEAM - HARINGEY, Burgoyne Road Clinic, 58A Burgoyne Road, N4 1AE </br></br>Treatment and support to children and young people aged from 0-18 years with mental health, behavioural and emotional needs.</br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101x00f">Click here for more info</a>').addTo(NHSservices),
    L.marker([51.594871, -0.071294], {icon: blueMarker}).bindPopup('<img src="https://dl.dropboxusercontent.com/u/69787788/NHS_icon.png" width="100" height="90"></br> THE GROVE DRUG TREATMENT SERVICE - HARINGEY, 9 Bruce Grove, N17 6RA</br></br>Provision a wide range of treatment services to people experiencing problems with drugs misuse in Haringey.</br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101y003">Click here for more info</a>').addTo(NHSservices),
    L.marker([51.658026, -0.089926], {icon: blueMarker}).bindPopup('<img src="https://dl.dropboxusercontent.com/u/69787788/NHS_icon.png" width="100" height="90"></br> CONTINUING CARE FOR OLDER ADULTS, Bay Tree House, Christ Church Close, Enfield, EN2 6NZ</br></br>They provide rehabilitation care to older adults with severe and enduring mental health needs in a residential setting.</br></br><a target="_blank" href="http://www.beh-mht.nhs.uk/Default.aspx?locid=01u01500100101w006">Click here for more info</a>').addTo(NHSservices),
    L.marker([51.546676, -0.174895], {icon: blueMarker}).bindPopup('<img src="https://dl.dropboxusercontent.com/u/69787788/NHS_icon.png" width="100" height="90"></br> THE TAVISTOCK AND PORTMAN NHS FOUNDATION TRUST, Tavistock Centre, 120 Belsize Lane, NW3 5BA</br></br>Provides culturally sensitive support to refugees and asylum-seeking children, young people and families in Barnet, Camden, Enfield and Haringey.</br></br><a target="_blank" href="https://tavistockandportman.nhs.uk/care-and-treatment/our-clinical-services/refugee-service/">Click here for more info</a>').addTo(NHSservices);



var greenIcon = new LeafIcon({iconUrl: 'https://dl.dropboxusercontent.com/u/69787788/green_marker.png'});

var charity = new L.LayerGroup();

    L.marker([51.568234, -0.133067], {icon: greenIcon}).bindPopup('<img src="http://www.nafsiyat.org.uk/Images/Logo.png" width="190" height="80"></br>NAFSIYAT Intercultural Therapy Centre, Unit 4, Lysander Mews, Lysander Grove, N19 3QP </br></br>Nafsiyat offers short-term intercultural therapy to people from diverse backgrounds who live in Islington, Enfield, Camden and Haringey. They provide therapy in 24 languages</br></br><a target="_blank" href="http://www.nafsiyat.org.uk">Click here for more info</a>').addTo(charity),
	L.marker([51.598993, -0.068026], {icon: greenIcon}).bindPopup('<img src="https://dl.dropboxusercontent.com/u/69787788/open-door-logo-blue.jpg" width="140" height="40"></br>OPEN DOOR - Tottenham, 639 Enterprise Centre, 639 High Road, Tottenham, N17 8AA on the corner of Lordship Lane</br></br>They offer a range of evidence-based therapies including: Counselling, Psychodynamic Psychotherapy, Cognitive Behavioural Therapy (CBT), Mindfulness Based Therapy, Interpersonal Therapy for Adolescents (IPT-A), Dynamic Interpersonal Therapy (DIT), Family Therapy, Group Therapy. They also have a number of specialist services including: a Psychotherapy Service for young people with special needs, a secondary school therapy service, the Parenting Teenagers Project for parents of young people aged 12-21</br></br><a target="_blank" href="https://opendooronline.org">Click here for more info</a>').addTo(charity),
	L.marker([51.566143, -0.112009], {icon: greenIcon}).bindPopup('<img src="https://dl.dropboxusercontent.com/u/69787788/Maytree_logo.jpg" width="180" height="70"></br>MAYTREE - 72 Moray Road, Finsbury Park, N4 3LG </br></br>Maytree aims to alleviate suffering and help people in suicidal crisis to re-engage with life and to restore hope.</br></br><a target="_blank" href="http://maytree.org.uk">Click here for more info</a>').addTo(charity),
	L.marker([51.595528, -0.109610], {icon: greenIcon}).bindPopup('<img src="http://www.modernism-in-metroland.co.uk/uploads/1/0/2/5/10257505/1362146.jpg?906" width="250" height="200"></br>WOOD GREEN LIBRARY (2nd floor), 187-197A High Road, Wood Green, N22 6XD</br></br>Wood Green Library hosts the folliwing mental health services providers:</br></br><a target="_blank" href="http://www.wisethoughts.org">WISE THOUGHTS</a></br></br><a target="_blank" href="www.haringey.gov.uk">HARINGEY ADULT LEARNING SERVICE (For info enter Adult Learning Service into the search)</a></br></br><a target="_blank" href="www.haringey.gov.uk">WOOD GREEN CARERS HUB (For info enter Wood Green Carers Hub into the search)</a>').addTo(charity),
	L.marker([51.577393, -0.082986], {icon: greenIcon}).bindPopup('<img src="http://www.haga.co.uk/wp-content/uploads/2014/10/HAGA-logo-e1464174063896.png" width="140" height="60"></br>HAGA - Action on Alcool - Haringey Recovery Service, 590 Seven Sisters Road, N15 6HR</br></br>Haringey Advisory Group on Alcohol</br></br><a target="_blank" href="http://www.haga.co.uk">Click here for more info</a>').addTo(charity),
	L.marker([51.606376, -0.270731], {icon: greenIcon}).bindPopup('<img src="https://dl.dropboxusercontent.com/u/69787788/alzheimers_society.jpeg" width="180" height="120"></br>ALZHEIMERS SOCIETY - Barnet, Enfield and Haringey - Room 135, Edgware Community Hospital, Burnt Oak Broadway, Edgware, HA8 0AD</br></br>Alzheimer’s Society is currently providing the following services in Haringey Dementia Café takes place weekly on Wednesday’s at the Hornsey Housing Trust, Abyssinia Court, Weston Park, N8 from 2pm to 4pm. Please contact 0207 561 4820 for further information. Singing for the Brain – weekly, (12 week terms) on Thursday afternoons 2pm to 4pm at Haringey Irish Centre, Pretoria Road, Tottenham N17 8DX. Please call for further information</br></br><a target="_blank" href="https://www.alzheimers.org.uk">Click here for more info</a>').addTo(charity),
	L.marker([51.585938, -0.115220], {icon: greenIcon}).bindPopup('<img src="http://www.arboursassociation.org/wp-content/uploads/arbours-newlogo1b-400.jpg" width="140" height="60"></br>THE ARBOURS ASSOCIATION - Arbours Psychotherapy Service, 6 Church Lane, London, N8 7BU</br></br>Long term Residential therapeutic community. Medium term crisis residential facility, alternative to hospital.</br></br><a target="_blank" href="http://www.arboursassociation.org">Click here for more info</a>').addTo(charity),
	L.marker([51.591694, -0.149385], {icon: greenIcon}).bindPopup('<img src="http://highgatecounselling.org.uk/wp-content/uploads/2015/11/logo.jpg" width="140" height="60"></br>HIGHGATE COUNSELLING CENTRE - Tetherdown Halls, Tetherdown, N10 1ND</br></br>They offer affordable counselling, train new counsellors and offer clinical placements. Ther mission is to offer help with emotional and relationship problems and to provide a gateway to the counselling profession via the delivery of the training.</br></br><a target="_blank" href="http://highgatecounselling.org.uk">Click here for more info</a>').addTo(charity),
	L.marker([51.581960, -0.061574], {icon: greenIcon}).bindPopup('<img src="https://markfield.org.uk/wp-content/uploads/2016/09/Markfield-logo.png" width="140" height="60"></br>MARKFIELD PROJECT - Markfield Park, Markfield Road, N15 4RB</br></br>They offer a range of after school clubs and holiday playschemes where disabled and non-disabled children play together. Daytime and evening social clubs for adults with learning disabilities, autism or Aspergers Syndrome include dance, art, trips and discussion groups.</br></br><a target="_blank" href="https://markfield.org.uk/">Click here for more info</a>').addTo(charity),
	L.marker([51.607487, -0.078152], {icon: greenIcon}).bindPopup('<img src="http://www.selbytrust.co.uk/sites/all/themes/selby/logo.png" width="200" height="60"></br>HARINGEY SOMALI COMMUNITY & CULTURAL ASSOCIATION - South block, 1st floor, The Selby Centre, Selby Road, N17 8JL</br></br>Information and advice for the Somali community. Advice on a wide range of subjects including welfare benefits, housing, immigration, education, employment and health.</br></br><a target="_blank" href="http://www.selbytrust.co.uk/haringey-somali-community-cultural-association-hscca">Click here for more info</a>').addTo(charity),
	L.marker([51.544970, -0.122593], {icon: greenIcon}).bindPopup('<img src="http://solacewomensaid.org/wp-content/themes/solace/images/logo.png" width="150" height="60"></br>SOLACE WOMENs AID - Unit 5-7, Blenheim Court, 62 Brewery Road, N7 9NY</br></br>Emotional support to women aged 16 and over who have been affected by domestic and sexual violence in an intimate relationship. Sessions are offered during the day or in the evening.</br></br><a target="_blank" href="http://solacewomensaid.org/get-help/haringey/">Click here for more info</a>').addTo(charity),
	L.marker([51.567045, -0.114699], {icon: greenIcon}).bindPopup('<img src="http://www.refugeetherapy.org.uk/media/200/logo.jpg" width="180" height="60"></br>REFUGEE THERAPY CENTRE - 1A Leeds Place, Tollington Park, N4 3RF</br></br>Psychotherapeutic help for refugees and asylum seekers, especially children and families of recently arrived refugees who are having problems of adjustment.</br></br><a target="_blank" href="http://www.refugeetherapy.org.uk/">Click here for more info</a>').addTo(charity),
	L.marker([51.582157, -0.126676], {icon: greenIcon}).bindPopup('<img src="https://dl.dropboxusercontent.com/u/69787788/relate.jpeg" width="150" height="60"></br>RELATE (NORTH EAST LONDON) - 84 Park Road, Crouch End</br></br>Relationship support for individuals, couples, families, children and young people. They provide relationship counselling, sex therapy and mediation among other services. In addition, they run short courses for parents designed to help them understand the impact ongoing parental conflict can have on their children</br></br><a target="_blank" href="https://www.relate.org.uk/london-north-east">Click here for more info</a>').addTo(charity),
	L.marker([51.578058, -0.125647], {icon: greenIcon}).bindPopup('<img src="http://www.hwfonline.org.uk/ee/images/logo.png" width="180" height="80"></br>HARINGEY WOMENs FORUM- 8a Edison Road, N8 8AE</br></br>Advice, counselling and housing support for women in Haringey</br></br><a target="_blank" href="http://www.hwfonline.org.uk/">Click here for more info</a>').addTo(charity),
	L.marker([51.591090, -0.227239], {icon: greenIcon}).bindPopup('<img src="https://dl.dropboxusercontent.com/u/69787788/cmha.jpeg" width="290" height="50"></br>CHINESE MENTAL HEALTH ASSOCIATION, Meritage Centre, Church End, Hendon, NW4 4JT</br></br>A range of support for Chinese people including befriending, counselling and employment support. In addition they provide support for carers who may not be familiar with traditional Chinese culture</br></br><a target="_blank" href="http://www.cmha.org.uk/">Click here for more info</a>').addTo(charity),
	L.marker([51.546825, -0.087012], {icon: greenIcon}).bindPopup('<img src="https://dl.dropboxusercontent.com/u/69787788/Imece.jpeg" width="180" height="90"></br>IMECE WOMENs CENTRE, 2 Newington Green Road, Islington, N1 4RX</br></br>The non-profit organisation aims to empower women by providing culturally sensitive services. They assist Turkish women survivors of violence, including harmful practices such as forced marriage and honour based violence. Imece offers one-to-one and group counselling, in addition to psycho-education. </br></br><a target="_blank" href="www.imece.org.uk ">Click here for more info</a>').addTo(charity),
	L.marker([51.594877, -0.071304], {icon: greenIcon}).bindPopup('<img src="http://www.talktofrank.com/sites/all/themes/frank/logo.png" width="150" height="70"></br>BUBIC (Bringing Unity Back Into The Community)- First Floor, 9 Bruce Grove, Tottenham, N176RA - 020 8808 6550   -   frank@talktofrank.com</br></br>The organisation provides support for drug users, ex-drug users, their family and friends. You can drop-in and have your needs assessed and a package of peer support and mentoring will be put in place by staff and volunteers. </br></br><a target="_blank" href="http://www.talktofrank.com">Click here for more info</a>').addTo(charity),
	L.marker([51.597332, -0.253103], {icon: greenIcon}).bindPopup('<img src="https://www.rethink.org/images/logo.png" width="80" height="80"></br>RETHINK MENTAL HEALTH - Elysian House, Charcot Road, Off Colindale Avenue, Barnet, NW9 5DH</br></br>Rethink nationally run an advice helpline, advocacy, carer support, employment, training, and services dedicated to black and minority ethnic communities. Their community support services, offer people the help they need to regain confidence to engage in everyday social and workplace activities. In addition, they run support groups throughout the country. You’re able to find out what runs in your area on their website.</br></br><a target="_blank" href="www.rethink.org">Click here for more info</a>').addTo(charity),
	L.marker([51.602751, -0.059956], {icon: greenIcon}).bindPopup('<img src="http://2.bp.blogspot.com/-yu18mVx2ZYY/Us6isNSpHuI/AAAAAAAAArs/Tat2DYOsrew/s1600/luos%2Bblog%2Bbanner%2B2014.png" width="300" height="80"></br>LIVING UNDER ONE SUN - WELL PARK LANE, 177 Park Lane, Tottenham, N17 OHJ - 020 8801 6868</br></br>The organisation creates a place for communities to meet, share skills, and shape their neighbourhoods together. They have various activites which run regularly for people of all backgrounds and age groups. This including yoga, football, athletics, knitting groups and more.</br></br><a target="_blank" href="http://livingunder1sun.blogspot.co.uk/">Click here for more info</a>').addTo(charity),
	L.marker([51.580991, -0.123496], {icon: greenIcon}).bindPopup('<img src="https://dl.dropboxusercontent.com/u/69787788/open-door-logo-blue.jpg" width="140" height="40"></br> OPEN DOOR (Crouch End), 12 Middle Lane, Crouch End, London N8 8PL</br></br>They offer a range of evidence-based therapies including: Counselling, Psychodynamic Psychotherapy, Cognitive Behavioural Therapy (CBT), Mindfulness Based Therapy, Interpersonal Therapy for Adolescents (IPT-A), Dynamic Interpersonal Therapy (DIT), Family Therapy, Group Therapy. They also have a number of specialist services including: a Psychotherapy Service for young people with special needs, a secondary school therapy service, the Parenting Teenagers Project for parents of young people aged 12-21</br></br><a target="_blank" href="https://opendooronline.org">Click here for more info</a>').addTo(charity);

	

    var mbAttr = 'Map data &copy; <a href="http://openstreetmap.org">OpenStreetMap</a> contributors, ' +
			'<a href="http://creativecommons.org/licenses/by-sa/2.0/">A-Team</a>, ' +
			'Imagery © <a href="http://mapbox.com">Mapbox</a>',
		mbUrl = 'https://{s}.tiles.mapbox.com/v3/{id}/{z}/{x}/{y}.png';

    var grayscale   = L.tileLayer(mbUrl, {id: 'santinska/ciuhbl03g00072inoafxhppps', attribution: mbAttr}),
	    streets  = L.tileLayer(mbUrl, {id: 'santinska.l7np8p7j',   attribution: mbAttr});

	var map = L.map('map', {
		center: [51.590906, -0.107912],
		zoom: 12,
		layers: [streets, boundary, communityassets, NHSservices, charity]
	});

	var baseLayers = {
		"Grayscale": grayscale,
		"Colour Map": streets
	};

	var overlays = {
		"Haringey borough boundary": boundary,
		"Haringey Council mental health services": communityassets,
		"NHS mental health services": NHSservices,
		"Charity or voluntary sector mental health services": charity
		
	};

	L.control.layers(baseLayers, overlays).addTo(map);

</script>	
</body>
</html>
