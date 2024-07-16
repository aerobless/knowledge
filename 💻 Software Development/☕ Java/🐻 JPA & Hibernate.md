# Common Linking Use Cases

## Many to Many

ACCOUNT 1..\* to POSITION 1..\* via a mapping Table ACCOUNT\_POSITION

```java
// Account class

@ManyToMany(cascade = Cascade.ALL, fetch FetchType.EAGER)
@LazyCollection(LazyCollection.FALSE)
@Fetch(FetchMode.SUBSELECT)
@JoinTable(inverseJoinColumns = @JoinColumn(name = "POSITION_ID"))
private List<Position> positions;
```

## One to One

`POSITION` to `POSITION_EXTENSION` without mapping table. `POSITION_EXTENSION` holds the ID referring to POSITION. `POSITION_EXTENSION` entries are only created if necessary.

```java
// PositionExtension class
@OneToOne(cascade = CascadeType.ALL)
@JoinColumn(name = "POSITION_ID")
private Position position;

// Position class (reverse mapping)
// mappedBy refers to class variable
@OneToOne(mappedBy = "position", cascade = CascadeType.ALL)
private PositionExtension positionsExtension;
```

# Troubleshooting

* Check if one or more persistence.xml exist that need to contain the new entities
* Do the entities have an empty default constructor for JPA? e.g. `Position(){}`
