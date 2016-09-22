# JChess

Sep 21
This is my first time making a java game. The purpose of this is to review, revisit and learn new Java concepts.

So far we have 5 classes and an enum.
Classes: Board, Move, Tile, Knight, Piece.
Enum: Alliance.

Here is a short description about the contents of each class:
Tile
This is an abstract class. Abstract classes are basically classes in which you can enter abstract methods. Abstract methods are methods which are declared in a class but are not implemented. Abstract classes may not be instantiated but they have subclasses. For example, we have 2 abstract methods called isTileOccupied(), and getPiece(). These are not defined in the class. But there are 2 subclasses of the Tile class, EmptyTile & OccupiedTile. They each have @Override methods which return something for those methods.
We also have a createAllPossibleEmptyTiles() method which creates 64 empty tiles in a Map. A Map is an interface that stores objects with a paired value. In our case, the object is an empty tile and the key is the tile coordinate. We also used a google library 'Guava' to make the map immutable. So when the tiles are made and stored in the map, the function will return an immutable copy of the map so that users cannot change anything on their own.

Piece
A piece is another abstract class. It is used to describe all the pieces on the board. They each have two main properties, piecePosition & pieceAlliance. Also, there is an abstract method called calculateLegalMoves(). This is not defined in this class. This method will calculate all the legal moves for a piece. The method is not defined here as all pieces have different legal moves. So we can actually create a new class for each piece and have this method defined differently for each type of piece yet have the same function.

Knight
The Knight is a class that extends the Piece class. This means that it is a subclass of the Piece class and inherits all of its properties. A class can only extend from one other class, i.e. the Knight class cannot extend from any other class now that it extends from the Piece class. This is different from 'implements'. Implements means that you are using the elements of an interface in your class. I guess it is similar to 'import'. You can implement as many interfaces as we want.
The knight class has its own version of the calculateLegalMoves(). We need a list to store all the legal moves. So we are using an array list. Arraylists are different from arrays as they can be resized after initialization if its capacity is reached.
I initally created an array with all the possible moves a knight can make, which I counted based on the rules of chess. The calculateLegalMoves() method will iterate through these possible coordinates and add or subtract them from its current coordinate. If it is a valid coordinate (it is on the board), then we have to check if that tile is occupied. If it is occupied then we have to check if it is of the same alliance or not. If it of the opposite alliance, or the tile is empty, then it is a legal move. Otherwise it is not.
This classs structure will be similar to all the different types of pieces.

