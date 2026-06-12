# Palabras clave de la API de Búsqueda

Considere usar nuestro nuevo paquete de Python, asf_search. asf_search puede usarse para realizar búsquedas del catálogo de ASF, y ofrece funcionalidad de línea base (baseline) y soporte de descarga. Además, se proporcionan numerosas constantes para facilitar el proceso de búsqueda. Actualmente, proporcionamos constantes para plataforma, instrumento, modo de haz, dirección de vuelo, polarización y nivel de procesamiento. Puede encontrar más información [aquí](/asf_search/basics).

Las palabras clave se usan para encontrar los datos deseados. Use tantas o tan pocas palabras clave como necesite. A continuación se enumeran las palabras clave y descripciones disponibles para cada endpoint de la API de Búsqueda. **Las palabras clave distinguen entre mayúsculas y minúsculas.**

*Note:* Cualquier error se devolverá en formato JSON.

## Endpoint de búsqueda
<https://api.daac.asf.alaska.edu/services/search/param>

### Parámetros del conjunto de datos
- <span style="color: #236192; font-size: 20px;">dataset</span>
    - Esta es la palabra clave alternativa preferida para búsquedas por “platform”.
    - Esta palabra clave tiene constantes provistas a través de asf_search. Puede encontrar más información [aquí](/asf_search/searching/#keywords).
    - Plataforma de teledetección que adquirió los datos. Puede especificar un valor único o una lista de valores.
    - Ejemplo:
        - dataset=SENTINEL-1
        - dataset=OPERA-S1
        - dataset=AIRSAR,UAVSAR
    - Valores:
        - NISAR, [SENTINEL-1](/datasets/using_ASF_data/#sentinel-1), [SLC-BURST](/datasets/using_ASF_data/#sentinel-1-bursts), [OPERA-S1](/datasets/using_ASF_data/#opera-sentinel-1), [ALOS PALSAR](/datasets/using_ASF_data/#alos-palsar), [ALOS AVNIR-2](/datasets/using_ASF_data/#alos-avnir-2), [SIR-C](/datasets/using_ASF_data/#sir-c), [ARIA S1 GUNW](/datasets/using_ASF_data/#aria-s1-gunw), [SMAP](/datasets/using_ASF_data/#smap-soil-moisture-active-passive), [UAVSAR](/datasets/using_ASF_data/#uavsar), [RADARSAT-1](/datasets/using_ASF_data/#radarsat-1), [ERS](/datasets/using_ASF_data/#ers), [JERS-1](/datasets/using_ASF_data/#jers), [AIRSAR](/datasets/using_ASF_data/#airsar), [SEASAT](/datasets/using_ASF_data/#seasat)

- <span style="color: #236192; font-size: 20px;">platform</span>
    - Véase también “dataset”. Dataset es la palabra clave preferida cuando sea posible.
    - Esta palabra clave tiene constantes provistas a través de asf_search. Puede encontrar más información [aquí](/asf_search/searching/#keywords).
    - Véase también “instrument”.
    - Plataforma de teledetección que adquirió los datos. Sentinel-1 y ERS tienen múltiples plataformas de teledetección, y usted puede elegir si especifica una plataforma específica. Puede especificar un valor único o una lista de valores.
    - Ejemplo:
        - platform=ALOS
        - platform=SA,SB
        - platform=S1
    - Valores:
        - NISAR, ALOS, A3, AIRSAR, AS, ERS, ERS-1, E1, ERS-2, E2, JERS-1, J1, RADARSAT-1, R1, SEASAT, SS, S1, Sentinel, Sentinel-1, Sentinel-1A, SA, Sentinel-1B, Sentinel-1 Interferogram (BETA), SB, SIR-C, SMAP, SP, UAVSAR, UA

- <span style="color: #236192; font-size: 20px;">instrument</span>
    - Véase también “dataset”. Dataset es la palabra clave preferida cuando sea posible.
    - Esta palabra clave tiene constantes provistas a través de asf_search. Puede encontrar más información [aquí](/asf_search/searching/#keywords).
    - Véase también “platform”.
    - Instrumento de teledetección que adquirió los datos. Para algunas plataformas, como ALOS, hay varios instrumentos entre los que elegir.
    - Ejemplo:
        - ALOS: instrument=PALSAR
        - ALOS: instrument=AVNIR-2
    - Valores:
        - C-SAR, PALSAR, AVNIR-2

- <span style="color: #236192; font-size: 20px; font-size: 20px;">absoluteOrbit</span>
    - Esta palabra clave también está disponible a través de [asf_search](/asf_search/searching/#searching).
    - Para ALOS, ERS-1, ERS-2, JERS-1, RADARSAT-1, Sentinel-1A y Sentinel-1B este valor corresponde al conteo de la órbita dentro del ciclo orbital. Para UAVSAR es el [Flight ID](https://uavsar.jpl.nasa.gov/cgi-bin/data.pl?_ga=2.34282209.1335434931.1620087198-1930115146.1605056035). Puede especificar un valor único, un rango de valores o una lista de valores.
    - Ejemplo:
        - RADARSAT: absoluteOrbit=25436
        - PALSAR: absoluteOrbit=25436-25445,25450
        - UAVSAR: absoluteOrbit=12006

- <span style="color: #236192; font-size: 20px;">asfframe</span>
    - Esta palabra clave también está disponible a través de [asf_search](/asf_search/searching/#searching).
    - Véase también “frame”.
    - Esto es principalmente una referencia de marco de ASF / [JAXA](https://global.jaxa.jp/). Sin embargo, algunas plataformas usan otras convenciones. Puede especificar un valor único, un rango de valores o una lista de valores.
    - Ejemplo:
        - asfframe=300 o asfframe=2845-2855 o asfframe=2800,2845-2855
    - Valores:
        - ERS, JERS, RADARSAT: marcos ASF de 0 a 900
        - ALOS PALSAR: marcos JAXA de 0 a 7200
        - SEASAT: marcos tipo ESA de 0208 a 3458 (debe usarse un cero inicial para los marcos 208–999)
        - Sentinel-1: valores internos de 0 a 1184

- <span style="color: #236192; font-size: 20px;">maxBaselinePerp</span>
    - Para análisis SAR interferométrico (InSAR), la Línea Base Perpendicular es la distancia espacial entre la primera y la segunda observación medida perpendicular a la dirección de observación del satélite y proporciona una indicación de la sensibilidad a la altura topográfica.
    - Funciona para ERS-1, ERS-2, JERS, RADARSAT-1, ALOS PALSAR. (No Sentinel-1)
    - Ejemplo:
        - maxBaselinePerp=1500 o maxBaselinePerp=50.5

- <span style="color: #236192; font-size: 20px;">minBaselinePerp</span>
    - Para análisis SAR interferométrico (InSAR), la Línea Base Perpendicular es la distancia espacial entre la primera y la segunda observación medida perpendicular a la dirección de observación del satélite y proporciona una indicación de la sensibilidad a la altura topográfica.
    - Funciona para ERS-1, ERS-2, JERS, RADARSAT-1, ALOS PALSAR. (No Sentinel-1)
    - Ejemplo:
        - minBaselinePerp=100 o minBaselinePerp=50.5

- <span style="color: #236192; font-size: 20px;">beamMode</span>
    - Esta palabra clave tiene constantes provistas a través de asf_search. Puede encontrar más información [aquí](/asf_search/searching/#keywords).
    - Modo de haz utilizado para adquirir los datos. Véase también beamSwath. Puede especificar un valor único o una lista de valores.
    - Ejemplo:
        - beamMode=FBS o beamMode=EW,IW o beamMode=ScanSAR+Wide
    - Valores:
        - AIRSAR: 3FP, ATI, XTI
        - ALOS: FBD, FBS, PLR, WB1, WB2, DSN
        - ERS-1: Standard, STD
        - ERS-2: Standard, STD
        - JERS-1: Standard, STD
        - RADARSAT-1: Standard, STD, Fine, High, Low, Wide, Narrow, ScanSAR+Wide, ScanSAR+Narrow
        - SEASAT: Standard, STD
        - SMAP: Standard, STD
        - Sentinel-1A: EW, IW, S1, S2, S3, S4, S5, S6, WV
        - Sentinel-1B: EW, IW, S1, S2, S3, S4, S5, S6, WV
        - UAVSAR: POL, RPI

- <span style="color: #236192; font-size: 20px;">beamSwath</span>
    - Esta palabra clave también está disponible a través de [asf_search](/asf_search/searching/#searching).
    - BeamSwath abarca un ángulo de observación y un modo de haz. Puede especificar un valor único o una lista de valores.
    - Ejemplo:
        - beamSwath=0
        - beamSwath=FN1, FN2, FN3, FN4, FN5
    - Valores:
        - AIRSAR: 3FP, ATI, XTI
        - ALOS: 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 15, 16, 17, 18, 19, 20
        - AVNIR-2: OBS
        - ERS-1: STD
        - ERS-2: STD
        - JERS-1: STD
        - RADARSAT-1: FN1, FN2, FN3, FN4, FN5, SNA, SNB, ST1, ST2, ST3, ST4, ST5, ST6, ST7, SWA, SWB, WD1, WD2, WD3, EH3, EH4, EH6, EL1
        - SEASAT: STD
        - Sentinel-1A: EW, IW, S1, S2, S3, S4, S5, S6, SLC, WV
        - Sentinel-1B: EW, IW, S1, S2, S3, S4, S5, S6, SLC, WV
        - UAVSAR: POL, RPI

- <span style="color: #236192; font-size: 20px;">collectionName</span>
    - Esta palabra clave también está disponible a través de [asf_search](/asf_search/searching/#searching).
    - Solo para colecciones de datos UAVSAR y AIRSAR. Busque por el nombre de la misión/campaña. Puede especificar un valor único. Para una lista de colecciones disponibles, consulte el endpoint de lista de misiones más abajo.
    - Ejemplo:
        - UAVSAR: collectionName=ABoVE
        - AIRSAR: collectionName=collectionName=Akiyoshi,+Japan

- <span style="color: #236192; font-size: 20px;">maxDoppler</span>
    - Esta palabra clave también está disponible a través de [asf_search](/asf_search/searching/#searching).
    - El Doppler proporciona una indicación de cuánto se desvía la dirección de observación de la adquisición ideal perpendicular a la dirección de vuelo.
    - Ejemplo:
        - maxDoppler=1500 o maxDoppler=1500.5

- <span style="color: #236192; font-size: 20px;">minDoppler</span>
    - Esta palabra clave también está disponible a través de [asf_search](/asf_search/searching/#searching).
    - El Doppler proporciona una indicación de cuánto se desvía la dirección de observación de la adquisición ideal perpendicular a la dirección de vuelo.
    - Ejemplo:
        - minDoppler=100 o minDoppler=1500.5

- <span style="color: #236192; font-size: 20px;">maxFaradayRotation</span>
    - Esta palabra clave también está disponible a través de [asf_search](/asf_search/searching/#searching).
    - La rotación del plano de polarización de la señal de radar impacta la imagen. Las señales HH y HV se mezclan. Las rotaciones unidireccionales que exceden 5° probablemente reduzcan significativamente la precisión de la recuperación de parámetros geofísicos, como la biomasa forestal.
    - Ejemplo:
        - maxFaradayRotation=3.5

- <span style="color: #236192; font-size: 20px;">minFaradayRotation</span>
    - Esta palabra clave también está disponible a través de [asf_search](/asf_search/searching/#searching).
    - La rotación del plano de polarización de la señal de radar impacta la imagen. Las señales HH y HV se mezclan. Las rotaciones unidireccionales que exceden 5° probablemente reduzcan significativamente la precisión de la recuperación de parámetros geofísicos, como la biomasa forestal.
    - Ejemplo:
        - minFaradayRotation=2

- <span style="color: #236192; font-size: 20px;">flightDirection</span>
    - Esta palabra clave tiene constantes provistas a través de asf_search. Puede encontrar más información [aquí](/asf_search/searching/#keywords).
    - Dirección de la órbita del satélite durante la adquisición de datos. Puede especificar un valor único.
    - Ejemplo:
        - flightDirection=DESCENDING
    - Valores:
        - A, ASC, ASCENDING, D, DESC, DESCENDING

- <span style="color: #236192; font-size: 20px;">flightLine</span>
    - Esta palabra clave también está disponible a través de [asf_search](/asf_search/searching/#searching).
    - Especifique una línea de vuelo para UAVSAR o AIRSAR. Puede especificar un valor único.
    - Ejemplo:
        - UAVSAR: flightLine=05901
        - AIRSAR: flightLine=gilmorecreek045-1.93044

- <span style="color: #236192; font-size: 20px;">frame</span>
    - Esta palabra clave también está disponible a través de [asf_search](/asf_search/searching/#searching).
    - Véase también “asfframe”.
    - Los marcos referenciados por la ESA se ofrecen para brindar a los usuarios una convención de enmarcado universal. A cada marco de la ESA se le asigna un marco ASF correspondiente. Puede especificar un valor único, un rango de valores o una lista de valores.
    - Ejemplo:
        - frame=300
        - frame=300-400
        - frame=300,303,305
        - frame=300,303,305-315
    - Valores:
        - Cualquier número de 0 a 7200.

- <span style="color: #236192; font-size: 20px;">frameCoverage</span>
    - Usado para el conjunto de datos NISAR. Especifica si el producto cubre el marco NISAR completo o si es cobertura parcial. Puede especificar un valor único.
    - Ejemplo: 
        - frameCoverage='FULL'
    - Valores:
        - FULL, PARTIAL

- <span style="color: #236192; font-size: 20px;">fullBurstID</span>
    - Usado para [productos de ráfaga de Sentinel-1](/datasets/using_ASF_data/#sentinel-1-bursts). Cada valor representa todos los productos de ráfaga sobre una sola subfranja, correspondiente a una pila casi perfectamente alineada con el marco. Este valor es útil para apilado de línea base. Puede especificar un valor único o una lista de valores.
    - Ejemplo:
        - valor único: fullBurstID=017_034465_IW2
        - lista de valores: fullBurstID=017_034465_IW2,079_167884_IW1

- <span style="color: #236192; font-size: 20px;">granule_list</span>
    - Lista separada por comas de escenas (gránulos) específicas. Las listas grandes deberán utilizar una [POST request](https://en.wikipedia.org/wiki/POST_(HTTP)).
    - admite consultas con comodines (`*` para coincidir con cualquier número de caracteres y `?` para coincidencias de un solo carácter), pero requiere establecer `maxresults` o usar asf-search directamente para resultados no acotados. Consulte [uso de comodines](/datasets/wildcard_usage/) para ver ejemplos de uso.
    - granule_list no puede usarse junto con otras palabras clave; sin embargo, puede usarse con la palabra clave output.
    - Ejemplo:
        - granule_list=ALPSRP111041130,
        S1B_IW_GRDH_1SDV_20161124T032008_20161124T032033_003095_005430_9906

- <span style="color: #236192; font-size: 20px;">groupid</span>
    - Esta palabra clave también está disponible a través de [asf_search](/asf_search/searching/#searching).
    - Lista separada por comas de IDs de grupo específicos. Para algunos conjuntos de datos, el group ID es el mismo que el nombre de la escena. Para otros, como Sentinel-1, el group ID es único para un grupo de escenas. El valor group ID se incluye en las salidas GeoJSON, JSON y CSV.
    - Ejemplo:
        - groupid=S1A_IWDV_0112_0118_037147_150

- <span style="color: #236192; font-size: 20px;">jointObservation</span>
    - Usado para el conjunto de datos NISAR. Especifica si los productos son adquisiciones simultáneas en banda L y banda S. True se usa para adquisiciones simultáneas.
- *Nota:* Los datos de banda S están disponibles a través de [Bhoonidhi de ISRO](https://bhoonidhi.nrsc.gov.in/bhoonidhi/home.html)
    - Ejemplo:
        - jointObservation=True
    - Valores: 
        - True, False

- <span style="color: #236192; font-size: 20px;">lookDirection</span>
    - Esta palabra clave también está disponible a través de [asf_search](/asf_search/searching/#searching).
    - Dirección izquierda o derecha de la adquisición de datos. Puede especificar un valor único.
    - Ejemplo:
        - lookDirection=L
    - Valores:
        - R, RIGHT, L, LEFT

- <span style="color: #236192; font-size: 20px;">maxInsarStackSize</span>
    - Una pila InSAR está compuesta por todos los gránulos SAR que cubren la misma región geográfica, son de la misma plataforma y fueron adquiridos con el mismo modo de haz, ángulo de observación y ancho de banda. Para obtener pilas InSAR que contengan un cierto número de gránulos SAR, especifique un mínimo, un máximo o ambos.
    - Funciona para ERS-1, ERS-2, JERS, RADARSAT-1, ALOS PALSAR. (No Sentinel-1)
    - Ejemplo:
        - maxInsarStackSize=175

- <span style="color: #236192; font-size: 20px;">minInsarStackSize</span>
    - Una pila InSAR está compuesta por todos los gránulos SAR que cubren la misma región geográfica, son de la misma plataforma y fueron adquiridos con el mismo modo de haz, ángulo de observación y ancho de banda. Para obtener pilas InSAR que contengan un cierto número de gránulos SAR, especifique un mínimo, un máximo o ambos.
    - Funciona para ERS-1, ERS-2, JERS, RADARSAT-1, ALOS PALSAR. (No Sentinel-1)
    - Ejemplo:
        - minInsarStackSize=20

- <span style="color: #236192; font-size: 20px;">offNadirAngle</span>
    - Esta palabra clave también está disponible a través de [asf_search](/asf_search/searching/#searching).
    - Ángulos fuera del nadir para ALOS PALSAR. Puede especificar un valor único, un rango de valores o una lista de valores.
    - Ejemplo:
        - offNadirAngle=21.5
        - offNadirAngle=9.7-14
        - offNadirAngle=21.5,23.1,20.5-24.2
    - Valores:
        - Más comunes: 21.5, 23.1, 27.1, 34.3
        - Otros: 9.7, 9.9, 13.8, 14, 16.2, 17.3, 17.9, 18, 19.2, 20.5, 21.5, 23.1, 24.2, 24.6, 25.2, 25.8, 25.9, 26.2, 27.1, 28.8, 30.8, 34.3, 36.9, 38.8, 41.5, 43.4, 45.2, 46.6, 47.8, 49, 50, 50.8

- <span style="color: #236192; font-size: 20px;">operaBurstID</span>
    - Usado para [productos Opera-S1](/datasets/using_ASF_data/#opera-sentinel-1). Cada valor identifica la ráfaga específica para el producto. Puede especificar un valor único o una lista de valores. 
    - Ejemplo:
        - valor único: operaBurstID=T078-165486-IW2
        - lista de valores: operaBurstID=T078_165486_IW2, T078_165485_IW2

- <span style="color: #236192; font-size: 20px;">polarization</span>
    - Esta palabra clave tiene constantes provistas a través de asf_search. Puede encontrar más información [aquí](/asf_search/searching/#keywords).
    - Propiedad de las ondas electromagnéticas SAR que puede usarse para extraer información significativa sobre las propiedades de la superficie terrestre. Puede especificar un valor único o una lista de valores.
    - Ejemplo:
        - polarization=VV
        - polarization=VV,HH
        - polarization=VV+VH
        - polarization=Dual+VV
    - Valores:
        - AIRSAR: FULL
        - ALOS: QUADRATURE, HH+5SCAN, HH, HH+4SCAN, VV, HH+3SCAN, FULL, HH+HV, VV+VH
        - ERS-1: VV
        - ERS-2: VV
        - JERS-1: HH
        - RADARSAT-1: HH
        - SEASAT: HH
        - Sentinel-1A: VV, VV+VH, Dual VV, VV+VH, Dual HV, Dual HH, HH, HH+HV, VV, Dual VH
        - Sentinel-1B: VV, VV+VH, Dual VV, VV+VH, Dual HV, Dual HH, HH, HH+HV, VV, Dual VH
        - UAVSAR: FULL, HH

- <span style="color: #236192; font-size: 20px;">mainBandPolarization</span>
    - Esta palabra clave tiene constantes provistas a través de asf_search. Puede encontrar más información [aquí](/asf_search/searching/#keywords).
    - Usado para el conjunto de datos NISAR. Main Band Polarization también se conoce como Frequency A Polarization.
    - Propiedad de las ondas electromagnéticas SAR que puede usarse para extraer información significativa sobre las propiedades de la superficie terrestre. Puede especificar un valor único o una lista de valores.
    - Ejemplo:
        - mainBandPolarization=HH
    - Valores:
        - NISAR: HH, HH+HV, HH+VV, HH+HV+VH+VV, VV, VV+VH, LH+LV, RH+RV

- <span style="color: #236192; font-size: 20px;">sideBandPolarization</span>
    - Esta palabra clave tiene constantes provistas a través de asf_search. Puede encontrar más información [aquí](/asf_search/searching/#keywords).
    - Usado para el conjunto de datos NISAR. Side Band Polarization también se conoce como Frequency B Polarization.
    - Propiedad de las ondas electromagnéticas SAR que puede usarse para extraer información significativa sobre las propiedades de la superficie terrestre. Puede especificar un valor único o una lista de valores.
    - Ejemplo:
        - sideBandPolarization=HH
    - Valores:
        - NISAR: HH, HH+HV, HH+HV+VH+VV, VV, VV+VH, LH+LV, RH+RV

- <span style="color: #236192; font-size: 20px;">processingLevel</span>
    - Esta palabra clave tiene constantes provistas a través de asf_search. Puede encontrar más información [aquí](/asf_search/searching/#keywords).
    - Nivel hasta el cual los datos han sido procesados; también tipo de producto.
        - Para el conjunto de datos NISAR, processingLevel es el Science Product.
    - Puede especificar un valor único o una lista de valores.
    - Ejemplo:
        - processingLevel=L0,L1
    - Valores:
        - NISAR: L0B, RSLC, RIFG, RUNW, ROFF, GSLC, GCOV, GUNW, GOFF, SME2
        - AIRSAR: 3FP, LTIF, PTIF, CTIF, PSTOKES, DEM, CSTOKES, JPG, LSTOKES
        - ALOS: L1.0, L1.1, L1.5, L2.2, RTC_LOW_RES, RTC_HI_RES, KMZ
        - ERS-1: L0, L1
        - ERS-2: L0, L1
        - JERS-1: L0, L1
        - OPERA-S1: RTC, CSLC, RTC_STATIC, CSLS_STATIC
        - RADARSAT-1: L0, L1
        - SEASAT: L1, GEOTIFF
        - Sentinel-1A: GRD_HS, GRD_HD, GRD_MS, GRD_MD, GRD_FD, SLC, RAW, OCN, METADATA_RAW, METADATA_SLC, METADATA_GRD_HD, METADATA_GRD_MD, METADATA_GRD_MS, METADATA_GRD_HS, METADATA_OCN
        - Sentinel-1B: GRD_HS, GRD_HD, GRD_MS, GRD_MD, GRD_FD, SLC, RAW, OCN, METADATA_RAW, METADATA_SLC, METADATA_GRD_HD, METADATA_GRD_MD, METADATA_GRD_MS, METADATA_GRD_HS, METADATA_OCN
        - Sentinel-1 InSAR: GUNW_STD, GUNW_AMP, GUNW_CON, GUN_COH, GUNW_UNW
        - Sentinel-1 Bursts: BURST
        - SIR-C: SLC, METADATA_SLC
        - SMAP: L1A_Radar_RO_QA, L1A_Radar_RO_HDF5, L1B_S0_LoRes_HDF5, L1B_S0_LoRes_QA, L1B_S0_LoRes_ISO_XML, L1A_Radar_QA, L1A_Radar_RO_ISO_XML, L1C_S0_HiRes_ISO_XML, L1C_S0_HiRes_QA, L1C_S0_HiRes_HDF5, L1A_Radar_HDF5
        - UAVSAR: KMZ, PROJECTED, PAULI, PROJECTED_ML5X5, STOKES, AMPLITUDE, COMPLEX, DEM_TIFF, PROJECTED_ML3X3, METADATA, AMPLITUDE_GRD, INTERFEROMETRY, INTERFEROMETRY_GRD, INC, SLOPE

- <span style="color: #236192; font-size: 20px;">product_list</span>
    - Lista separada por comas de archivos específicos (productos). Las listas grandes deberán utilizar una [POST request](https://en.wikipedia.org/wiki/POST_(HTTP)). Puede encontrar los valores de product_list para cualquier archivo en las salidas GeoJSON (fileID) o JSON (product_file_id). También está disponible desde CMR, en el campo granuleUR. Se garantiza que es un identificador único en CMR. ¡También puede encontrar el valor product_list en Vertex! Consulte la [página de Cookbook](/api/cookbook) para este consejo y más.
    - product_list no puede usarse junto con otras palabras clave; sin embargo, puede usarse con la palabra clave output.
    - Ejemplo:
        - product_list=ALAV2A276512920,
        S1A_IW_SLC__1SDV_20210614T154839_20210614T154905_038338_048643_D7E4-SLC

- <span style="color: #236192; font-size: 20px;">productionConfiguration</span>
    - Esta palabra clave tiene constantes provistas a través de asf_search. Puede encontrar más información [aquí](/asf_search/searching/#keywords).
    - Usado para el conjunto de datos NISAR para especificar la tubería de procesamiento usada para la escena. Puede especificar un valor único o una lista de valores.
        - Production o PR usa el sistema estándar de producción.
        - Urgent Response o UR es procesamiento sensible al tiempo en respuesta a eventos de respuesta urgente.
        - Custom o OD es procesamiento iniciado por el usuario fuera del sistema nominal de producción.
    - Ejemplo: 
        - productionConfiguration=UR
    - Valores:
        - PR, UR, OD

- <span style="color: #236192; font-size: 20px;">rangeBandwidth</span>
    - Esta palabra clave tiene constantes provistas a través de asf_search. Puede encontrar más información [aquí](/asf_search/searching/#keywords).
    - Usado para el conjunto de datos NISAR para especificar el ancho de banda en MHz. Puede especificar un valor único o una lista de valores. 
    - Algunos productos tienen un rango para la banda principal y la banda secundaria. Estos se indican como “[Ancho de banda de la banda principal]+[Ancho de banda de la banda secundaria]”.
    - Ejemplo: 
        - rangeBandwidth=20+5
    - Valores:
        - L-Band: 20, 40, 20+5, 40+5, 77, 5, 5+5
[//]: # (        - S-Band: 10, 25, 37, 75)

- <span style="color: #236192; font-size: 20px;">relativeOrbit</span>
    - Esta palabra clave también está disponible a través de [asf_search](/asf_search/searching/#searching).
    - Trayectoria u órbita del satélite durante la adquisición de datos. Para UAVSAR es el [Line ID](https://uavsar.jpl.nasa.gov/cgi-bin/data.pl?_ga=2.201268782.1252483948.1620685771-1930115146.1605056035). Puede especificar un valor único, un rango de valores o una lista de valores.
    - Ejemplo:
        - relativeOrbit=500,550-580
        - UAVSAR: relativeOrbit=05905
    - Valores:
        - ALOS: 1-671
        - ERS-1: 0-2410
        - ERS-2: 0-500
        - JERS-1: 0-658
        - RADARSAT-1: 0-342
        - SEASAT: 1-243
        - UAVSAR: varios

### Parámetros geoespaciales
- <span style="color: #236192; font-size: 20px;">bbox</span>
	- *Deprecation Notice:* Esta palabra clave será desaprobada. Use “intersectsWith” en su lugar.
	- Las cajas delimitadoras (bounding boxes) definen un área usando dos puntos long/lat. Los parámetros de la bounding box son 4 números separados por comas: longitud,latitud de la esquina inferior izquierda; y longitud,latitud de la esquina superior derecha. Es una gran opción para áreas de búsqueda muy amplias.
	- Ejemplo:
		- bbox=-150.2,65.0,-150.1,65.5

- <span style="color: #236192; font-size: 20px;">intersectsWith</span>
	- Esta palabra clave también está disponible a través de [asf_search](/asf_search/searching/#searching).
	- Búsqueda por polígono, segmento de línea (“linestring”) o punto definido en WKT 2D (Well-Known Text). Cada polígono debe estar explícitamente cerrado, es decir, el primer vértice y el último vértice de cada polígono listado deben ser idénticos. Los pares de coordenadas para cada vértice están en grados decimales: la longitud va seguida de la latitud.
	- Notas:
		- No admite multi-polígono, multi-línea ni multi-punto.
 		- Los agujeros de polígono se ignoran
 		- Esta palabra clave también acepta una [POST request](https://en.wikipedia.org/wiki/POST_(HTTP))
 	- Ejemplo (*Nota: los espacios y paréntesis de abajo deben codificarse en URL primero*):
 		- intersectsWith=polygon((-119.543 37.925, -118.443 37.7421, -118.682 36.8525, -119.77 37.0352, -119.543 37.925 ))
		- intersectsWith=linestring(-119.543 37.925, -118.443 37.7421)
		- intersectsWith=point(-119.543, 37.925)
	- Correctamente codificado en URL:
		- intersectsWith=point%28-119.543+37.925%29

- <span style="color: #236192; font-size: 20px;">polygon</span>
	- *Deprecation Notice:* Esta palabra clave será desaprobada. Use “intersectsWith” en su lugar.
	- Polígono delimitador en formato digital long/lat; introduzca las coordenadas en sentido antihorario y repita el primer punto al final para cerrar el polígono: en el formato ABCDA
	- Ejemplo:
		- polygon=-155.08,65.82,-153.5,61.91,-149.50,63.07,-149.94,64.55,-153.28,64.47,-155.08,65.82

#### Validación de forma
Si el AOI especificado es su propio Rectángulo Mínimo Envolvente (MBR) en una proyección de Mercator, los resultados de la búsqueda devueltos se intersectarán con el AOI en una proyección de Mercator, independientemente del ancho. Esto sigue siendo cierto incluso si se cruza la línea internacional de cambio de fecha dentro del AOI.

Para que un AOI sea considerado su propio MBR, debe cumplir con los siguientes criterios:

  - Cada vértice comparte una latitud o longitud con sus vecinos
  - Los puntos Este/Oeste comparten longitud
  - Los puntos Norte/Sur comparten latitud

Los AOI que no cumplan con estos criterios tendrán sus puntos conectados a lo largo de [círculos máximos](https://es.wikipedia.org/wiki/C%C3%ADrculo_m%C3%A1ximo).

Además, todos los AOI se validan y luego se simplifican según sea necesario. El proceso para esto es:
 
  1. Validar el AOI de entrada. Si no es válido, se muestra un error.
  2. Fusionar formas superpuestas.
  3. Casco convexo.
  4. Cualquier valor de índice fuera de rango se maneja ajustándolo y envolviéndolo al rango válido de valores.
  5. Simplificar puntos según un umbral de proximidad. El objetivo es tener menos de 400 puntos.

Cada uno de estos pasos se realiza solo cuando es necesario para obtener un único contorno con menos de 400 puntos. Cualquier paso innecesario se omite.

**Ejemplos de validación y simplificación:**

- Se proporciona un polígono que se auto-intersecta: 
	- Se muestra un error.
- Se proporciona un único contorno que consta de 1000 puntos:
	- Se usa una versión simplificada del mismo contorno, que consta de menos de 400 puntos.
- Se proporcionan múltiples geometrías, todas ellas superpuestas al menos en parte:
	- Se devuelve un único contorno que representa el contorno de todas las formas combinadas.
- Se proporcionan múltiples geometrías, al menos algunas de ellas completamente no superpuestas:
	- Se devuelve un único contorno que representa el casco convexo de todas las formas juntas.

### Parámetros temporales
- <span style="color: #236192; font-size: 20px;">processingDate</span>
	- Esta palabra clave también está disponible a través de [asf_search](/asf_search/searching/#searching).
	- Limita los resultados a registros que han sido procesados en ASF desde una fecha y/u hora dada.
	- Ejemplo:
		- processingDate=2017-01-01T00:00:00UTC

- <span style="color: #236192; font-size: 20px;">start</span>
	- Esta palabra clave también está disponible a través de [asf_search](/asf_search/searching/#searching).
	- Fecha de adquisición de los datos. Puede usarse en combinación con “end”. Puede ingresar fechas en lenguaje natural o una marca de fecha y/u hora. Todas las horas están en UTC. Para más información sobre formatos de fecha aceptados, consulte el endpoint del analizador de fechas más abajo.
	- Ejemplo:
		- start=May+30,+2018
		- start=yesterday
		- start=2010-10-30T11:59:59Z
		- start=1+week+ago&end=now

- <span style="color: #236192; font-size: 20px;">end</span>
	- Esta palabra clave también está disponible a través de [asf_search](/asf_search/searching/#searching).
	- Fecha de adquisición de los datos. Puede usarse en combinación con “start”. Puede ingresar fechas en lenguaje natural o una marca de fecha y/u hora. Todas las horas están en UTC. Para más información sobre formatos de fecha aceptados, consulte el endpoint del analizador de fechas más abajo.
	- Ejemplo:
		- end=May+30,+2018
		- end=today
		- end=2021-04-30T11:59:59Z
		- start=1+week+ago&end=now

- <span style="color: #236192; font-size: 20px;">season</span>
	- Esta palabra clave también está disponible a través de [asf_search](/asf_search/searching/#searching).
	- Día de inicio y fin del año para el rango estacional deseado. Esta palabra clave puede usarse junto con start/end para especificar un rango estacional dentro de un rango de fechas general. Los valores se basan en el calendario juliano. Debe especificar tanto una fecha de inicio de temporada como una de fin de temporada.
	- Ejemplo:
		- season=1,31
		- season=45,67
		- season=360,10
	- Valores:
		- Del 1 al 365

### Parámetros de resultados
- <span style="color: #236192; font-size: 20px;">output</span>
	- Formato deseado de los resultados de la API de Búsqueda. Si no se especifica, el formato predeterminado es metalink. El formato preferido es geoJSON.
	- Ejemplo:
		- output=geojson
	- Valores:
		- geojson, python, csv, json, kml, metalink, count, download
	- Descripción:
        - GeoJSON es el formato de salida preferido. Si falta algún campo requerido, comuníquese con ASF usando la información de abajo o contacte al equipo directamente en <uaf-asf-discovery@alaska.edu>
        - Python proporcionará el fragmento de código necesario para ejecutar su búsqueda deseada usando asf_search
		- KML puede abrirse en Google Earth, ArcGIS Earth o un programa similar
		- Count devuelve el número de resultados de su consulta. No incluye información adicional. Usar la salida count puede ayudar a determinar si su consulta devolvió la cantidad correcta de resultados. Hay un límite de tiempo para ejecutar consultas de la API de Búsqueda. Consulte la [página de resolución de problemas](/api/troubleshooting) para más detalles.
		- Metalink proporciona información de descarga para las escenas devueltas por su consulta. No incluye metadatos.
		- Descarga devuelve un script de descarga masiva que incluye los archivos devueltos por la búsqueda. Consulte la [documentación de descarga masiva](https://asf.alaska.edu/how-to/data-tools/asf-bulk-data-download-options/) para una guía completa sobre el uso del script de descarga masiva.
		- JSON incluye metadatos de escena y URLs de productos. Si GeoJSON no satisface sus necesidades, JSON es el formato preferido para uso programático.
		- CSV también incluye metadatos de escena y URLs de productos. CSV devuelve menos campos que JSON.

- <span style="color: #236192; font-size: 20px;">maxResults</span>
	- Número máximo de registros de datos a devolver en su consulta.
	- Ejemplo:
		- maxResults=10

## Endpoint de línea base (Baseline)
<https://api.daac.asf.alaska.edu/services/search/baseline>

- <span style="color: #236192; font-size: 20px;">reference</span>
	- Esta es la única palabra clave obligatoria. Ingrese el nombre de la escena de referencia para la cual desea ver resultados de línea base.
	- Ejemplo:
		- reference=S1B_IW_SLC__1SDV_20210704T135937_20210704T140004_027645_034CB0_4B2C

- <span style="color: #236192; font-size: 20px;">processingLevel</span>
	- Nivel hasta el cual los datos han sido procesados. Los datos de línea base solo están disponibles para ciertos niveles de procesamiento.
	- Ejemplo:
		- processingLevel=L1.5
	- Valores de processingLevel que contienen datos de línea base:
		- ALOS: L1.1, L1.5; predeterminado L1.1
		- ERS-1 y ERS-2: L0, L1; predeterminado L0
		- JERS-1: L0, L1; predeterminado L0
		- RADARSAT-1: L0, L1; predeterminado L0
		- Sentinel-1A y Sentinel-1B: SLC
		- Sentinel-1 Bursts: SLC

- <span style="color: #236192; font-size: 20px;">output</span>
	- Formato deseado de los resultados de la API de Búsqueda. Si no se especifica, el formato predeterminado es metalink. El formato preferido es geoJSON.
	- Ejemplo:
		- output=geojson
	- Valores:
		- geojson, python, csv, json, kml, metalink, count, download
	- Descripción:
		- GeoJSON es el formato de salida preferido. Si falta algún campo requerido, comuníquese con ASF usando la información de abajo o contacte al equipo directamente en <uaf-asf-discovery@alaska.edu>
		- Python proporcionará el fragmento de código necesario para ejecutar su búsqueda deseada usando asf_search
		- KML puede abrirse en Google Earth, ArcGIS Earth o un programa similar
		- Count devuelve el número de resultados de su consulta. No incluye información adicional. Usar la salida count puede ayudar a determinar si su consulta devolvió la cantidad correcta de resultados. Hay un límite de tiempo para ejecutar consultas de la API de Búsqueda. Consulte la [página de resolución de problemas](/api/troubleshooting) para más detalles.
		- Metalink proporciona información de descarga para las escenas devueltas por su consulta. No incluye metadatos.
		- Descarga devuelve un script de descarga masiva que incluye los archivos devueltos por la búsqueda. Consulte la [documentación de descarga masiva](https://asf.alaska.edu/how-to/data-tools/data-tools/#bulk_download) para una guía completa sobre el uso del script de descarga masiva.
		- JSON incluye metadatos de escena y URLs de productos. Si GeoJSON no satisface sus necesidades, JSON es el formato preferido para uso programático.
		- CSV también incluye metadatos de escena y URLs de productos. CSV devuelve menos campos que JSON.

- <span style="color: #236192; font-size: 20px;">maxResults</span>
	- Número máximo de registros de datos a devolver en su consulta.
	- Ejemplo:
		- maxResults=10

## Endpoint de validación WKT
<https://api.daac.asf.alaska.edu/services/utils/wkt>

Este endpoint validará y reparará una entrada WKT. La salida WKT reparada es cómo la API de Búsqueda interpretará la WKT proporcionada. Si una WKT no puede repararse, devolverá un error indicando el motivo. Todas las validaciones y errores se devuelven en formato JSON.

- <span style="color: #236192; font-size: 20px;">wkt</span>
	- Esta es la única palabra clave aceptada para este endpoint.
	- Ejemplo:
		- wkt=GEOMETRYCOLLECTION(POLYGON((46 -19,30 26,-3 41,22 39,49 16,46 -19)), POLYGON((27 24,12 4,18 31,27 24)))
		- En este ejemplo, la respuesta JSON enumerará los errores que fueron reparados y la WKT final “envuelta” y “no envuelta”.

## Endpoint de archivos geoespaciales a WKT

<https://api.daac.asf.alaska.edu/services/utils/files_to_wkt>

Este endpoint aceptará una [POST request](https://en.wikipedia.org/wiki/POST_(HTTP)) con archivos adjuntos. Devolverá la WKT analizada del archivo, así como la WKT reparada envuelta y no envuelta. Todas las salidas se devuelven en formato JSON. El formato de archivo preferido es geojson, pero la API de Búsqueda también admite otros formatos, como shapefile o kml.

Vea la [página de herramientas](/api/tools) para más detalles sobre POST requests.

- Ejemplo:
	- curl -X POST -F 'files=@/path/to/file' 'https://api.aac.asf.alaska.edu/services/utils/files_to_wkt'

## Endpoint del analizador de fechas
<https://api.daac.asf.alaska.edu/services/utils/date>

Este endpoint puede usarse para comprobar cómo se analizan las fechas por la API de Búsqueda. Todas las fechas analizadas se devuelven en formato JSON.

- <span style="color: #236192; font-size: 20px;">date</span>
	- Esta es la única palabra clave aceptada para este endpoint. Puede usar lenguaje natural, como “yesterday”, fechas con o sin marca de tiempo o días de la semana.

## Endpoint de lista de misiones
<https://api.daac.asf.alaska.edu/services/utils/mission_list>

Este endpoint enumera todas las misiones (también conocidas como campañas o colecciones) para todos los conjuntos de datos. Cualquiera de las misiones devueltas en la lista puede usarse como valor para la palabra clave collectionName en el endpoint de Búsqueda. La lista de misiones se devuelve en formato JSON.

- <span style="color: #236192; font-size: 20px;">platform</span>
	- Esta palabra clave es opcional. Si se usa, restringirá la lista de misiones a la(s) plataforma(s) especificada(s).
	- Plataforma de teledetección que adquirió los datos. Sentinel-1 y ERS tienen múltiples plataformas de teledetección, y usted puede elegir si especifica una plataforma específica. Puede especificar un valor único o una lista de valores.
	- Ejemplo:
		- platform=ALOS
		- platform=SA,SB
		- platform=S1
	- Valores:
		- ALOS, A3, AIRSAR, AS, ERS, ERS-1, E1, ERS-2, E2, JERS-1, J1, RADARSAT-1, R1, SEASAT, SS, S1, Sentinel, Sentinel-1, Sentinel-1A, SA, Sentinel-1B, Sentinel-1 Interferogram (BETA), SB, SMAP, SP, UAVSAR, UA

## Endpoint de estado (Health)
<https://api.daac.asf.alaska.edu/health>

Este endpoint se usa para comprobar el estado (health) de la API de Búsqueda. Se devuelve en formato JSON. No hay palabras clave asociadas con el endpoint de verificación de estado.

Además del estado de la API de Búsqueda, también devuelve configuraciones de la API de Búsqueda y el estado de salud de CMR.
