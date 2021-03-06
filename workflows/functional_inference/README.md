Functional inference 
====================

#### From ubuntu 16.04 using assembled contigs 

#### first, annotate your contigs with prokka
#### MegaHit contigs 
```
docker run -v ${PWD}:/data -it ummidock/prokka:1.12 prokka \
/data/megahit_output_podar_metaG_sub_10/final.contigs.fa --outdir /data/prokka_annotation --prefix podar_metaG_sub_10 
```
#### SPAdes contigs 
```
docker run -v ${PWD}:/data -it ummidock/prokka:1.12 prokka \
/data/megahit_output_podar_metaG_sub_10/contigs.fasta --outdir /data/prokka_annotation --prefix podar_metaG_sub_10 
```
#### next, link the data and run Abricate
#### MegaHit contigs 
```
docker run -v ${PWD}:/data -it thanhleviet/abricate abricate \
/data/megahit_output_podar_metaG_sub_10/final.contigs.fa > abricate_output_megahit_podar_metaG_sub_10.tab
```
#### SPAdes contigs 
```
docker run -v ${PWD}:/data -it thanhleviet/abricate abricate \
/data/spades_output_podar_metaG_sub_10/contigs.fasta > abricate_output_spades.tab
```
