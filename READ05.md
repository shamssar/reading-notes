# Sequelize-Normalization

here are three standard associations: One-To-One, One-To-Many and Many-To-Many


### Sequelize provides four types of associations that should be combined to create them:
- HasOne: A.hasOne(B): One-To-One relationship exists between A and B, with the foreign key being defined in the target model (B).
- BelongsTo: A.belognsTo(B): One-To-One relationship, with the foreign key being defined in the source model (A).
- HasMany: A.hasMany(B): One-To-Many relationship, with the foreign key being defined in the target model (B).
- BelongsToMany: A.belongsToMany(B, { through: 'C' }): Many-To-Many relationship exists between A and B, using table C as junction table, which will have the foreign keys (aId and bId, for example). Sequelize will automatically create this model C (unless it already exists) and define the appropriate foreign keys on it.
In previous example, we call A the source model and B the target model.

### To create a One-To-One relationship
the hasOne and belongsTo associations are used together;
### To create a One-To-Many relationship
the hasMany and belongsTo associations are used together
### To create a Many-To-Many relationship
two belongsToMany calls are used together.
