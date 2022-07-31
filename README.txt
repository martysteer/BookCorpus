The BookCorpus, or Toronto Book Corpus, has undergone a lot of use in the AI community, but it is also a contetntious dataset with respect to provenance, copyrights and redistribution rights.

This directory contains two variants of BookCorpus, one containing all the origian text files from Smashwords.com, and another containing preprocessed and concatendated text for training MLMs (machine learning models).

Here is a really interesting and quite complete online document about this corpus, which describes the provenance, data sources, access problems and research uses: https://gist.github.com/alvations/4d2278e5a5fbcf2e07f49315c4ec1110

This repo is my notes in retrieving and understanding the bookcorpus, combinit it with some metadata found in a different place, so I can retrieve some texts in a specific category.

---

"BookCorpus" smashwords txt file corpus
Filename: books1.tar.gz
Desc: This contains the smashwords original text files and URL list. No metadata. Only filenames.
git: https://github.com/soskek/bookcorpus
Social media source: https://twitter.com/theshawwn/status/1301852133319294976?s=21
Download source URL: https://battle.shawwn.com/sdb/books1/books1.tar.gz

---

"BookCorpus" preprocessed
Filename: bookcorus.tar.bz2
Desc: This contains the preprocessed and concatenated text files
Social media source: https://twitter.com/IgorBrigadir/status/1095075607178870786
Info about corpus:
- https://twitter.com/IgorBrigadir/status/1227628562594664448
- https://gist.github.com/alvations/4d2278e5a5fbcf2e07f49315c4ec1110
Google drive download URL: https://drive.google.com/file/d/16KCjV9z_FHm8LgZw05RSuk4EsAWPOP_z/view

---

Other contextual online information about this problematic corpus:
https://github.com/soskek/bookcorpus/issues/24#issuecomment-556024973
https://github.com/NVIDIA/DeepLearningExamples/issues/536
https://towardsdatascience.com/replicating-the-toronto-bookcorpus-dataset-a-write-up-44ea7b87d091

