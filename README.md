Culinary Knowledge Embeddings using BERT

Objective:
This project aims to leverage BERT embeddings to capture culinary knowledge embedded in recipe instructions and ingredient sections. The primary goals include generating average BERT embeddings for ingredients, calculating cosine similarity among ingredient pairs, and manual evaluation of top and bottom pairs based on a reproducible protocol.

Methodology:

1. Data Compilation:
- Combine data for 'South-American' cuisine based on the 'Recipe-ID' field, extracting 'RecipeID,' 'Ingredients,' and 'Recipe Instructions.'
- Input data:
  1. Top5_region.csv: Recipe ID and Regions for Top-5 Cuisines.
  2. Top5_region_Ingredients.csv: Ingredients & Recipe Instructions for each Recipe.
  3. tdata: Data with recipe IDs, Ingredients, and Ingredient Phrases for Top-5 cuisines.

2. Data Pre-Processing:
- Clean ingredients by converting multi-word ingredients into single words.
- Convert ingredients into meaningful sentences for better BERT context understanding.
- Clean recipe instructions by removing digits, extra spaces, punctuation, and special characters.
- Convert multi-word ingredients in instructions to single words.
- Divide instructions into sentences, resulting in 7697 clean instructions.

3. Count Ingredient Occurrences per Recipe Instruction:
- Tally occurrences of unique ingredients in all recipes, creating a dictionary with ingredients as keys and counts as values.

4. Calculate Bert Embeddings:
- Randomly sample 100 recipes for ingredients with over 100 occurrences; for others, consider all instructions.
- Use Embedding4BERT Library to calculate BERT embeddings for each ingredient.
- Average out BERT embeddings and save in a dictionary.

5. Cosine Similarity Among Ingredient Pairs:
- Use cosine similarity to determine similarity among all pairs of ingredients based on BERT embeddings.
- Store most similar pairs in a CSV named "most_similar_df_all_occ.csv."

6. Manual Verification of Bert Embeddings:
- Analyze the Top 200 and Bottom 200 ingredient pairs manually.
- Consider positive food pairing, flavor molecule sharing (verified on FlavorDB), and substitutes or generic forms of ingredients.
- Refer to online resources for alternative names or substitutes.
- Validate ingredient pairs belonging to the same category.

Files:
- Top5_region.csv
- Top5_region_Ingredients.csv
- tdata
- sa_all_ing_embeddings.pkl: BERT embeddings stored as a pickle file.
- most_similar_df_all_occ.csv: Cosine similarity results for ingredient pairs.

Conclusion:
This project provides insights into culinary knowledge through BERT embeddings, facilitating exploration of ingredient similarities and enhancing understanding of South-American cuisine. The manual verification process ensures the reliability of the generated embeddings.
