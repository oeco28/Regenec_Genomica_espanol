# Regenec_Genomica_español
Este es un repositorio en español donde estaré actualizando información acerca de herramientas de uso común para el análisis de datos genómicos

## Analysis de Calidad de las Secuencias

En este breve tutorial solo veremos como usar las herramientas de analisis de calidad de secuencias.
Las instrucciones en cajas seran aquella que pueden copiar y pegar en el termina para poder hacer los analysis.

La herramienta que usaremos para analyzar la calidad de las secuencias es FastQC (https://www.bioinformatics.babraham.ac.uk/projects/fastqc/)

ejemplo general:
```bash
  cd regenec_project/data/
  fastqc --noextract --nogroup --outdir path_to_fastq_files_dir Mi_archivo.fastq.gz
```
Los archivos a utilizar son: 
  1.  Purple_Early_1_GTCCGC_S8_L001_R1_001.fastq.gz
  2.  Purple_Early_1_GTCCGC_S8_L001_R2_001.fastq.gz
  
ejemplo_específico:
```bash
  cd regenec_project/data/
  fastqc --noextract --nogroup --outdir ./ Purple_Early_1_GTCCGC_S8_L001_R1_001.fastq.gz
```
